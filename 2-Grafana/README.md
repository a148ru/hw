## 1.

![alt text](image.png)

## 2.

```
node_load1{instance="node-exporter:9100"}
node_load5{instance="node-exporter:9100"}
node_load15{instance="node-exporter:9100"}


100 - (avg(irate(node_cpu_seconds_total{instance="node-exporter:9100", mode="idle"}[5m]))*100)

node_memory_MemTotal_bytes{instance="node-exporter:9100"} - node_memory_MemAvailable_bytes{instance="node-exporter:9100"}

node_filesystem_size_bytes{device="/dev/mapper/ubuntu--vg-ubuntu--lv"} - node_filesystem_free_bytes{device="/dev/mapper/ubuntu--vg-ubuntu--lv"}
```

![alt text](image-1.png)

## 3

![alt text](image-2.png)

## 4

```json
{
  "annotations": {
    "list": [
      {
        "builtIn": 1,
        "datasource": {
          "type": "grafana",
          "uid": "-- Grafana --"
        },
        "enable": true,
        "hide": true,
        "iconColor": "rgba(0, 211, 255, 1)",
        "name": "Annotations & Alerts",
        "type": "dashboard"
      }
    ]
  },
  "editable": true,
  "fiscalYearStartMonth": 0,
  "graphTooltip": 0,
  "id": 7,
  "links": [],
  "panels": [
    {
      "datasource": {
        "type": "prometheus",
        "uid": "becviq5jkl5ogb"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "palette-classic"
          },
          "custom": {
            "axisBorderShow": false,
            "axisCenteredZero": false,
            "axisColorMode": "text",
            "axisLabel": "",
            "axisPlacement": "auto",
            "barAlignment": 0,
            "barWidthFactor": 0.6,
            "drawStyle": "line",
            "fillOpacity": 0,
            "gradientMode": "none",
            "hideFrom": {
              "legend": false,
              "tooltip": false,
              "viz": false
            },
            "insertNulls": false,
            "lineInterpolation": "linear",
            "lineWidth": 1,
            "pointSize": 5,
            "scaleDistribution": {
              "type": "linear"
            },
            "showPoints": "auto",
            "spanNulls": false,
            "stacking": {
              "group": "A",
              "mode": "none"
            },
            "thresholdsStyle": {
              "mode": "off"
            }
          },
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              },
              {
                "color": "red",
                "value": 80
              }
            ]
          }
        },
        "overrides": []
      },
      "gridPos": {
        "h": 7,
        "w": 7,
        "x": 0,
        "y": 0
      },
      "id": 2,
      "options": {
        "legend": {
          "calcs": [],
          "displayMode": "list",
          "placement": "bottom",
          "showLegend": true
        },
        "tooltip": {
          "hideZeros": false,
          "mode": "single",
          "sort": "none"
        }
      },
      "pluginVersion": "11.5.1",
      "targets": [
        {
          "editorMode": "code",
          "expr": "node_load1{instance=\"node-exporter:9100\"}",
          "legendFormat": "__auto",
          "range": true,
          "refId": "A"
        },
        {
          "datasource": {
            "type": "prometheus",
            "uid": "becviq5jkl5ogb"
          },
          "disableTextWrap": false,
          "editorMode": "builder",
          "expr": "node_load5{instance=\"node-exporter:9100\"}",
          "fullMetaSearch": false,
          "hide": false,
          "includeNullMetadata": true,
          "instant": false,
          "legendFormat": "__auto",
          "range": true,
          "refId": "B",
          "useBackend": false
        },
        {
          "datasource": {
            "type": "prometheus",
            "uid": "becviq5jkl5ogb"
          },
          "editorMode": "code",
          "expr": "node_load15{instance=\"node-exporter:9100\"}",
          "hide": false,
          "instant": false,
          "legendFormat": "__auto",
          "range": true,
          "refId": "C"
        }
      ],
      "title": "CPU LoadAverage 1/5/15",
      "type": "timeseries"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "becviq5jkl5ogb"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "thresholds"
          },
          "custom": {
            "axisBorderShow": true,
            "axisCenteredZero": false,
            "axisColorMode": "series",
            "axisGridShow": false,
            "axisLabel": "",
            "axisPlacement": "auto",
            "barAlignment": 0,
            "barWidthFactor": 0.6,
            "drawStyle": "line",
            "fillOpacity": 25,
            "gradientMode": "opacity",
            "hideFrom": {
              "legend": false,
              "tooltip": false,
              "viz": false
            },
            "insertNulls": false,
            "lineInterpolation": "smooth",
            "lineStyle": {
              "fill": "solid"
            },
            "lineWidth": 3,
            "pointSize": 13,
            "scaleDistribution": {
              "type": "linear"
            },
            "showPoints": "auto",
            "spanNulls": false,
            "stacking": {
              "group": "A",
              "mode": "none"
            },
            "thresholdsStyle": {
              "mode": "off"
            }
          },
          "mappings": [],
          "thresholds": {
            "mode": "percentage",
            "steps": [
              {
                "color": "green",
                "value": null
              },
              {
                "color": "purple",
                "value": 30
              },
              {
                "color": "blue",
                "value": 50
              },
              {
                "color": "#6ED0E0",
                "value": 70
              },
              {
                "color": "#EAB839",
                "value": 80
              },
              {
                "color": "red",
                "value": 95
              }
            ]
          },
          "unit": "decbytes"
        },
        "overrides": []
      },
      "gridPos": {
        "h": 7,
        "w": 5,
        "x": 7,
        "y": 0
      },
      "id": 3,
      "options": {
        "legend": {
          "calcs": [],
          "displayMode": "list",
          "placement": "bottom",
          "showLegend": true
        },
        "tooltip": {
          "hideZeros": false,
          "mode": "single",
          "sort": "none"
        }
      },
      "pluginVersion": "11.5.1",
      "targets": [
        {
          "disableTextWrap": false,
          "editorMode": "code",
          "exemplar": false,
          "expr": "node_memory_MemTotal_bytes{instance=\"node-exporter:9100\"}",
          "format": "time_series",
          "fullMetaSearch": false,
          "hide": false,
          "includeNullMetadata": true,
          "instant": false,
          "interval": "",
          "legendFormat": "Memory usage",
          "range": true,
          "refId": "H",
          "useBackend": false
        },
        {
          "datasource": {
            "type": "prometheus",
            "uid": "becviq5jkl5ogb"
          },
          "editorMode": "code",
          "expr": "node_memory_MemTotal_bytes{instance=\"node-exporter:9100\"} - node_memory_MemAvailable_bytes{instance=\"node-exporter:9100\"}",
          "hide": false,
          "instant": false,
          "legendFormat": "Total memory",
          "range": true,
          "refId": "Q"
        }
      ],
      "title": "RAM",
      "type": "timeseries"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "becviq5jkl5ogb"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "fixedColor": "green",
            "mode": "fixed"
          },
          "displayName": "Ram usage",
          "fieldMinMax": false,
          "mappings": [],
          "thresholds": {
            "mode": "percentage",
            "steps": [
              {
                "color": "green",
                "value": null
              },
              {
                "color": "yellow",
                "value": 5
              },
              {
                "color": "orange",
                "value": 10
              },
              {
                "color": "red",
                "value": 16
              }
            ]
          },
          "unit": "decbytes"
        },
        "overrides": []
      },
      "gridPos": {
        "h": 7,
        "w": 3,
        "x": 12,
        "y": 0
      },
      "id": 7,
      "options": {
        "colorMode": "value",
        "graphMode": "area",
        "justifyMode": "auto",
        "orientation": "auto",
        "percentChangeColorMode": "standard",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "showPercentChange": false,
        "textMode": "auto",
        "wideLayout": true
      },
      "pluginVersion": "11.5.1",
      "targets": [
        {
          "disableTextWrap": false,
          "editorMode": "code",
          "expr": "node_memory_MemFree_bytes{instance=\"node-exporter:9100\"}",
          "fullMetaSearch": false,
          "includeNullMetadata": true,
          "legendFormat": "RAM Usage",
          "range": true,
          "refId": "A",
          "useBackend": false
        }
      ],
      "title": "Panel Title",
      "type": "stat"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "becviq5jkl5ogb"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "fixedColor": "green",
            "mode": "palette-classic"
          },
          "custom": {
            "axisBorderShow": false,
            "axisCenteredZero": false,
            "axisColorMode": "text",
            "axisLabel": "",
            "axisPlacement": "auto",
            "barAlignment": 0,
            "barWidthFactor": 0.6,
            "drawStyle": "line",
            "fillOpacity": 0,
            "gradientMode": "none",
            "hideFrom": {
              "legend": false,
              "tooltip": false,
              "viz": false
            },
            "insertNulls": false,
            "lineInterpolation": "smooth",
            "lineWidth": 1,
            "pointSize": 6,
            "scaleDistribution": {
              "type": "linear"
            },
            "showPoints": "auto",
            "spanNulls": false,
            "stacking": {
              "group": "A",
              "mode": "none"
            },
            "thresholdsStyle": {
              "mode": "off"
            }
          },
          "mappings": [],
          "max": 100,
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              },
              {
                "color": "blue",
                "value": 80
              },
              {
                "color": "#EAB839",
                "value": 90
              },
              {
                "color": "red",
                "value": 100
              }
            ]
          },
          "unit": "percent"
        },
        "overrides": []
      },
      "gridPos": {
        "h": 7,
        "w": 7,
        "x": 0,
        "y": 7
      },
      "id": 1,
      "options": {
        "legend": {
          "calcs": [],
          "displayMode": "list",
          "placement": "bottom",
          "showLegend": true
        },
        "tooltip": {
          "hideZeros": false,
          "mode": "single",
          "sort": "none"
        }
      },
      "pluginVersion": "11.5.1",
      "targets": [
        {
          "datasource": {
            "type": "prometheus",
            "uid": "becviq5jkl5ogb"
          },
          "disableTextWrap": false,
          "editorMode": "code",
          "expr": "100 - (avg(irate(node_cpu_seconds_total{instance=\"node-exporter:9100\", mode=\"idle\"}[5m]))*100)",
          "fullMetaSearch": false,
          "hide": false,
          "includeNullMetadata": true,
          "instant": false,
          "legendFormat": "__auto",
          "range": true,
          "refId": "B",
          "useBackend": false
        }
      ],
      "title": "CPU Usage",
      "type": "timeseries"
    },
    {
      "datasource": {
        "uid": "becviq5jkl5ogb"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "fixedColor": "purple",
            "mode": "shades"
          },
          "custom": {
            "hideFrom": {
              "legend": false,
              "tooltip": false,
              "viz": false
            }
          },
          "mappings": [],
          "unit": "bytes"
        },
        "overrides": []
      },
      "gridPos": {
        "h": 7,
        "w": 4,
        "x": 7,
        "y": 7
      },
      "id": 4,
      "options": {
        "displayLabels": [
          "name",
          "value",
          "percent"
        ],
        "legend": {
          "displayMode": "list",
          "placement": "bottom",
          "showLegend": true
        },
        "pieType": "pie",
        "reduceOptions": {
          "calcs": [
            "last"
          ],
          "fields": "",
          "values": false
        },
        "tooltip": {
          "hideZeros": false,
          "mode": "single",
          "sort": "none"
        }
      },
      "pluginVersion": "11.5.1",
      "targets": [
        {
          "disableTextWrap": false,
          "editorMode": "code",
          "exemplar": false,
          "expr": "node_filesystem_size_bytes{device=\"/dev/mapper/ubuntu--vg-ubuntu--lv\"} - node_filesystem_free_bytes{device=\"/dev/mapper/ubuntu--vg-ubuntu--lv\"}",
          "format": "heatmap",
          "fullMetaSearch": false,
          "includeNullMetadata": true,
          "instant": false,
          "legendFormat": "Usage space",
          "range": true,
          "refId": "Disk usage",
          "useBackend": false
        },
        {
          "datasource": {
            "type": "prometheus",
            "uid": "becviq5jkl5ogb"
          },
          "disableTextWrap": false,
          "editorMode": "code",
          "expr": "node_filesystem_free_bytes{device=\"/dev/mapper/ubuntu--vg-ubuntu--lv\"}",
          "format": "time_series",
          "fullMetaSearch": false,
          "hide": false,
          "includeNullMetadata": true,
          "instant": false,
          "legendFormat": "Free space",
          "range": true,
          "refId": "Free",
          "useBackend": false
        }
      ],
      "title": "Filesystem",
      "type": "piechart"
    }
  ],
  "preload": false,
  "refresh": "",
  "schemaVersion": 40,
  "tags": [],
  "templating": {
    "list": []
  },
  "time": {
    "from": "now-30m",
    "to": "now"
  },
  "timepicker": {},
  "timezone": "browser",
  "title": "Netology-HW-Monitoring",
  "uid": "aecz4pfyefi80d",
  "version": 27,
  "weekStart": ""
}
```