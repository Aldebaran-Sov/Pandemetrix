# Docker Compose Configuration

This directory contains Docker Compose configurations for deploying Pandemetrix across different geographical clusters. The architecture uses Docker Compose override functionality to provide both shared services and cluster-specific configurations.

## Overview

The Pandemetrix project supports deployment in three different clusters:

- **États-Unis (USA)**: Full feature set with high-scale data processing
- **France**: GDPR-compliant deployment with Dataviz integration
- **Suisse (Switzerland)**: Multi-language support without Dataviz

## File Structure

``` text
docker/
├── compose.yml              # Base services common to all clusters
├── compose.dataviz.yml      # Shared Dataviz solution (USA + France)
├── compose.usa.yml          # USA-specific overrides and services
├── compose.france.yml       # France-specific overrides and services
├── compose.switzerland.yml  # Switzerland-specific overrides and services
└── README.md               # This documentation
```

## Docker Compose Override Strategy

### Shared Dataviz Configuration (`compose.dataviz.yml`)

The `compose.dataviz.yml` file contains the Dataviz solution from MSPR1 that is **shared between USA and France clusters only**:

- **Dataviz Service**: Data visualization interface from MSPR1
- **Dataviz Database**: Specific database configurations for visualization data
- **Dataviz API**: REST API for chart data and dashboard functionality

### Base Configuration (`compose.yml`)

The main `compose.yml` file contains services that are **common to all clusters**:

- **Database**: PostgreSQL with shared schema
- **ETL Service**: Data processing pipeline
- **AI API Backend**: Core machine learning API
- **Frontend Base**: application base configuration
- **Monitoring**: for observability

### Cluster-Specific Overrides

Each cluster has its own override file that:

1. **Modifies** existing services from the base configuration
2. **Adds** cluster-specific services
3. **Removes** services not needed for that cluster
4. **Configures** environment variables and volumes

## Usage

### Starting a Specific Cluster

Use Docker Compose with multiple files to deploy a cluster:

```bash
# Deploy USA cluster (with Dataviz)
docker compose -f compose.yml -f compose.dataviz.yml -f compose.usa.yml up -d

# Deploy France cluster (with Dataviz)
docker compose -f compose.yml -f compose.dataviz.yml -f compose.france.yml up -d

# Deploy Switzerland cluster (without Dataviz)
docker compose -f compose.yml -f compose.switzerland.yml up -d
```

### Development Mode

For development with live reload:

```bash
# USA cluster in development mode (with Dataviz)
docker compose -f compose.yml -f compose.dataviz.yml -f compose.usa.yml up --build

# France cluster in development mode (with Dataviz)
docker compose -f compose.yml -f compose.dataviz.yml -f compose.france.yml up --build

# Switzerland cluster in development mode (without Dataviz)
docker compose -f compose.yml -f compose.switzerland.yml up --build
```

### Stopping Services

```bash
# Stop USA cluster
docker compose -f compose.yml -f compose.usa.yml down

# Stop with volume cleanup
docker compose -f compose.yml -f compose.france.yml down -v
```

## Cluster Configurations

### USA Cluster (`compose.usa.yml`)

**Specific Features:**

- High-performance database configuration for large datasets
- Additional API Technical service from MSPR1
- Enhanced Dataviz solution integration
- Horizontal scaling for AI services

**Additional Services:**

- `api-technical`: Legacy API from MSPR1
- `dataviz-mspr1`: Data visualization service
- `redis`: Caching layer for performance
- `load-balancer`: NGINX for traffic distribution

**Environment Variables:**

```yaml
CLUSTER_REGION=usa
DB_MAX_CONNECTIONS=200
AI_WORKERS=4
ENABLE_DATAVIZ=true
ENABLE_API_TECHNICAL=true
```

### France Cluster (`compose.france.yml`)

**Specific Features:**

- GDPR compliance configurations
- French language support
- Mobile-optimized frontend
- Enhanced security and data encryption
- Dataviz integration (without API Technical)

**Additional Services:**

- `gdpr-compliance`: Data protection service
- `dataviz-mspr1`: Data visualization (GDPR-compliant)
- `security-scanner`: Automated security checks

**Environment Variables:**

```yaml
CLUSTER_REGION=france
LANGUAGE=fr
GDPR_ENABLED=true
MOBILE_OPTIMIZED=true
ENABLE_DATAVIZ=true
ENABLE_API_TECHNICAL=false
DATA_ENCRYPTION=true
```

### Switzerland Cluster (`compose.switzerland.yml`)

**Specific Features:**

- Multi-language support (French, German, Italian)
- Simplified architecture (no Dataviz, no API Technical)
- Swiss data residency compliance
- Lightweight deployment

**Services Removed:**

- Dataviz service (not included)
- API Technical (not included)

**Environment Variables:**

``` yaml
CLUSTER_REGION=switzerland
LANGUAGES=fr,de,it
DEFAULT_LANGUAGE=fr
ENABLE_DATAVIZ=false
ENABLE_API_TECHNICAL=false
DATA_RESIDENCY=switzerland
```

### Cluster-Specific Dataviz Configurations

While the core Dataviz service is shared, each cluster can have specific configurations:

#### USA Cluster Dataviz

- High-performance charting for large datasets
- Advanced analytics dashboards
- Real-time data streaming capabilities

#### France Cluster Dataviz

- GDPR-compliant data visualization
- French language interface
- Mobile-responsive charts for public access
- Data anonymization for public dashboards
