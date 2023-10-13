# Certificate Measurement Data

## Introduction

This repository contains data on the TLS certificate checking behavior of random Internet clients, obtained through an adnet campaign.

## Data Description

* Format: JSON lines
* Fields:
  * `host`: The subdomain with which the TLS handshake was performed. Each subdomain uses a different certificate:
    * `base`: Fully valid certificate
    * `rev`: Revoked certificate
    * `sta`: Revoked certificate with a valid OCSP status provided via OCSP Stapling
    * `mus`: Certificate with the Must-Staple flag, but served without a stapled OCSP status
    * `sct`: Certificate without Signed Certificate Timestamps (SCTs)
  * `user_agent`: The User-Agent string of the requesting client
  * `rid`: Randomly generated request ID, used to tie together individual requests that are part of the same client measurement
  * `timestamp`: ISO-formatted datetime string from the time the request was made
  * `country`: Originating country based on Maxmind geolite2 GeoIP-database
