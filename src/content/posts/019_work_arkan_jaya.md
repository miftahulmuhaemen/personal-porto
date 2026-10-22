---
title: 'Software Engineer at PT Arkan Jaya Nusantara'
pubDate: '2021-01-01'
category: 'work'
techStack: ['Go', 'TypeScript', 'React', 'MongoDB', 'Docker', 'GitHub Actions', 'Web Bluetooth']
---

- [x] Medical Telemetry Aggregator Shipped to MVP
- [x] Multi-Vendor Hardware GATT Protocols Reverse-Engineered

## Overview & Role Summary

PT Arkan Jaya Nusantara engineered connected healthcare and telemedicine platforms. As Software Engineer (January 2021 – November 2022, Banjarmasin), primary technical responsibilities focused on designing a continuous vital-sign monitoring aggregator, reverse-engineering hardware telemetry protocols across disparate Bluetooth Low Energy (BLE) medical devices, and establishing modern CI/CD deployment automation.

## Architecture and Engineering Implementation

### 1. Medical BLE Continuous Telemetry Aggregator

Medical monitoring requires continuous, loss-resilient sensor telemetry streams to ensure patient vital abnormalities are surfaced immediately:

- **Aggregator Architecture**: Built an event-driven telemetry ingestion engine in Go paired with MongoDB collections optimized for sequential time-series sensor readings.
- **Device Support Matrix**: Integrated multiple third-party medical peripherals, including pulse oximeters (SpO2 percentage, pulse rate, plethysmograph wave points), automated non-invasive blood pressure monitors (systolic, diastolic, mean arterial pressure), and continuous single-lead electrocardiogram (ECG) sensors.
- **Connection Management & Fault Tolerance**: Implemented automated peripheral reconnection state machines with exponential backoff, handling signal attenuation, packet loss, and frame reassembly during clinical transit. Improved data packet capture accuracy and transmission reliability by 25%.

### 2. Multi-Vendor Protocol Engineering & GATT Reverse Engineering

Medical peripheral manufacturers often utilize closed or poorly documented communication protocols:

- **Vendor Technical Liaison**: Collaborated with domestic and international device manufacturers to obtain technical specifications, firmware changelogs, and peripheral SDKs.
- **GATT Reverse Engineering**: For hardware lacking standardized documentation, analyzed raw Generic Attribute Profile (GATT) service UUIDs and characteristic notification streams.
- **Binary Stream Decoding**: Authored low-level byte decoders handling multi-byte endianness conversions, bitmask flags, status nibbles, and checksum (CRC) verifications to translate raw hex packets into validated, type-safe JSON payloads.

### 3. Clinician Monitoring Interface

- **React & TypeScript Dashboard**: Developed high-performance clinician workstation interfaces rendering real-time streaming vitals and historical trend charts.
- **Performance Optimization**: Employed canvas-based rendering for high-frequency ECG waveform streams and memoized virtualized lists for alert feeds, eliminating UI stutter under rapid device polling.

### 4. CI/CD Modernization & Containerization

- **Containerization**: Standardized development, testing, and production runtime environments using lightweight multi-stage Dockerfiles.
- **GitHub Actions Pipelines**: Configured automated CI/CD pipelines enforcing static analysis, unit test execution, and automated image builds, increasing release cadence and preventing regressions from reaching hospital testbeds.

## Measurable Engineering Outcomes

- **Reliability Metric**: Boosted telemetry data accuracy and transmission reliability by 25% across irregular wireless environments.
- **Interoperability**: Reverse-engineered and normalized data streams from 3+ distinct medical peripheral manufacturers into a unified clinical data model.
- **Operational Cadence**: Replaced manual SSH deployments with automated GitHub Actions workflows and Docker image registries.
