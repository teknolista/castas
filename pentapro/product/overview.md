# PRODUCT · Overview

Castas provides an informational 40-question affective-polarization test for people reflecting on attitudes toward opposing political groups. The native Android experience follows reference web content and behavior within documented platform scope; supported locales are Brazilian Portuguese, English and Spanish. See [features](features.md) and [UI design](../../docs/ui-design.md). This migration does not establish scientific validity, product acceptance or new test results.

## Migrated project record

## Purpose and users

Castas presents an informational 40-question affective-polarization test to people who want to reflect on emotional and social attitudes toward opposing political groups. The Android app should reproduce the behaviors and content of the Castas web project while using native Android screens.

## Canonical requirements

Behavioral requirements are maintained in [the PentaPRO feature contract](features.md). This file does not duplicate that contract.

## Evidence and scope

Reference evidence: `../../web/src/`, `../../docs/artifacts/wireframes/`, and `../../docs/artifacts/documents/`, inspected 2026-11-07. The app includes the home, test, result, about, political fanatic, terms, and privacy experiences; PT-BR, English, and Spanish.

## Decision note

The web About wireframe, Likert document, and executable scoring function now agree on 3/2/1/0. The Android About screen derives its labels from its scoring function. Existing Android scores use the same scale.
