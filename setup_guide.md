# ELK Stack SOC Lab Setup Guide 🔧

This guide will walk you through the entire process of setting up an ELK stack (Elasticsearch, Logstash, Kibana) for a SOC lab environment, from the initial installation to the final working setup. Please follow the steps sequentially, and if you run into any issues, refer to the troubleshooting section below.

---

## Step 1: Install Elasticsearch and Kibana

1. **Update your system**:  
    ```bash
    sudo apt update
    sudo apt upgrade
    ```

2. **Install Elasticsearch**:
    ```bash
    sudo apt install elasticsearch
    ```

3. **Install Kibana**:
    ```bash
    sudo apt install kibana
    ```

---

## Step 2: Configure Elasticsearch

- Navigate to the `elasticsearch.yml` file:
    ```bash
    sudo nano /etc/elasticsearch/elasticsearch.yml
    ```

- Make necessary changes for the cluster:
    ```yaml
    network.host: 0.0.0.0
    cluster.initial_master_nodes: ["localhost"]
    ```

- Restart Elasticsearch:
    ```bash
    sudo systemctl restart elasticsearch
    ```

---

## Step 3: Configure Kibana

- Edit the `kibana.yml` file:
    ```bash
    sudo nano /etc/kibana/kibana.yml
    ```

- Make changes for Kibana:
    ```yaml
    server.host: "0.0.0.0"
    elasticsearch.hosts: ["http://localhost:9200"]
    ```

- Restart Kibana:
    ```bash
    sudo systemctl restart kibana
    ```

---

## Step 4: Accessing Kibana

Once the services are up, navigate to Kibana by opening your browser and going to:
http://localhost:5601

---

## Step 5: Integrating Sample Data

1. In Kibana, go to **"Add Sample Data"** to load data sets for analysis (e.g., "Sample eCommerce data").
2. Follow the on-screen instructions to import the sample data into Kibana.

---

### Next Steps

1. You can configure additional integrations as per your needs.
2. Set up secure connections using SSL/TLS if required.

Refer to the **`troubleshooting.md`** if you run into any issues.

---

