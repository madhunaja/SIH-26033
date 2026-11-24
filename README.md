# Smart India Hackathon Workshop
# Date: 24/11/2026
## Reference Number: 26017177
## Name: Madhunaja N

## Problem Title
SIH 26033: Multiple inter mediaries reduce farmers earnings and increase consumer prices.

## Problem Creater's Organization
Ministry of Consumer Affairs, Food & Public Distribution

## Theme
Agriculture, FoodTech & Rural Development

## Problem Description
Expected Solution: Create a digital marketplace that:

• Connects farmers/FPOs directly with consumers and bulk buyers.
• Provides logistics support.
• Uses AI for demand forecasting and route optimization.

Benefits:

• Better prices for farmers.
• Lower prices for consumers.
• Reduced supply chain inefficiencies.

## Proposed Solution
Detailed ExplanationAgriDirect is an AI-driven, omnichannel farm-to-fork digital marketplace and logistics orchestration platform designed to connect Farmer Producer Organizations (FPOs) and individual farmers directly with retail consumers, HoReCa (Hotels, Restaurants, and Catering), and institutional bulk buyers. The platform consists of:

Multilingual Farmer & FPO App (with Voice/IVR Support): Allows farmers and FPO aggregators to list produce, check real-time mandi vs. platform benchmark prices, receive AI harvest-timing advisories, and schedule pickups.

Buyer Web & Mobile Portal: Enables retail households (via society/community group-buying) and B2B bulk buyers (supermarkets, restaurants, processors) to browse graded produce with full farm-to-table traceability and place scheduled or spot orders.

Integrated Micro-Logistics & Milk-Run Engine: Aggregates small farm-gate lots at village collection centers (FPO hubs) and assigns shared, temperature-appropriate transport vehicles using dynamic route optimization.

How It Addresses the Problem

Eliminates Multi-Tier Middlemen: Replaces the traditional 4–6 layer chain (village aggregator → local commission agent → APMC wholesaler → sub-wholesaler → retailer) with a single digital transaction layer, shifting middleman margins directly to farmers while lowering end-consumer prices.

Solves Fragmented Smallholder Logistics: Individual farmers lack the volume to hire dedicated transport. By clustering orders at the FPO level and routing shared vehicles, per-kilogram freight costs drop significantly.

Prevents Distress Sales & Price Volatility: AI demand forecasting informs FPOs of upcoming regional demand 7–14 days in advance, allowing coordinated harvesting and preventing market gluts or spoilage.

Innovation and Uniqueness

Hyperlocal Demand-Harvest Synchronization: Unlike passive e-commerce portals, the AI engine matches predicted regional consumption (factoring in festivals, weather, and historical buying patterns) with crop maturity timelines to trigger pre-harvest forward contracts.

Dynamic Multi-Stop Milk-Run Routing with Perishability Scoring: Routes vehicles not just by shortest distance, but by a Perishability-Weighted Vehicle Routing Problem (VRP) algorithm that prioritizes delicate produce (e.g., tomatoes, leafy greens) and dynamically fills return trips with agricultural inputs.

Low-Literacy Vernacular & Voice UX: Built with regional speech-to-text, visual icon-driven cataloging, and UPI/e-RUPI instant escrow settlement upon digital quality verification at the collection center.

## Technical Approach

Technologies to be Used

Frontend (Mobile & Web): React Native / Flutter (Android-first Farmer & Driver apps with offline-first SQLite caching); React.js / Next.js (Buyer B2B/B2C web portal and FPO Admin dashboard).

Backend & Microservices: Python (FastAPI) for AI/ML inference services; Node.js (NestJS) for high-concurrency order matching, real-time tracking, and payment orchestration.

Database & Caching: PostgreSQL with PostGIS (spatial queries and geofencing), Redis (real-time order book, dynamic pricing cache, and driver location state), and TimescaleDB (historical mandi price and weather time-series).

AI/ML & Optimization Stack:

Demand & Price Forecasting: Temporal Fusion Transformers (TFT) / Prophet + XGBoost trained on historical Agmarknet mandi arrivals, weather forecasts, and local calendar events.

Route Optimization: Google OR-Tools (Capacitated Vehicle Routing Problem with Time Windows — CVRPTW) integrated with OSRM / MapMyIndia APIs.

Automated Quality Grading: Lightweight MobileNetV3 / YOLOv8 computer vision model on the FPO app to classify produce size, color, and surface defects via smartphone camera.

Integrations & Infrastructure: ONDC (Open Network for Digital Commerce) protocol compatibility for wider buyer discovery, UPI/Razorpay Route for automated split settlements, Twilio/Bhashini APIs for vernacular voice/SMS alerts, and Docker/Kubernetes on AWS/GCP.

Methodology and Process for Implementation

[Farmer / FPO] ---> 1. Lists Harvest & AI Photo Grading (App / Voice)
                            |
                            v
[AI Core Engine] -> 2. Forecasts Demand & Matches Bulk/Retail Orders
                            |
                            v
[Logistics Engine] -> 3. Generates Milk-Run Pickup & Delivery Routes (OR-Tools)
                            |
                            v
[FPO Collection Hub] -> 4. Weighs, Verifies Quality & Triggers Instant UPI Escrow
                            |
                            v
[Consumer / Bulk Buyer] -> 5. Receives Traceable Produce & Confirms Delivery
Phase 1 — Core Marketplace & FPO Onboarding (Weeks 1–4): Build multilingual farmer/buyer interfaces, digital cataloging, e-KYC for FPOs, and escrow-backed UPI split payments.

Phase 2 — AI Forecasting & Computer Vision Grading (Weeks 5–8): Train demand forecasting models using Agmarknet datasets and deploy smartphone-based visual grading to standardize produce quality before dispatch.

Phase 3 — Logistics Optimization & Pilot Deployment (Weeks 9–12): Integrate OR-Tools CVRPTW routing, onboard local mini-truck/tempo fleets, and run a closed-loop pilot across 3–5 FPOs and 50+ retail/HoReCa buyers.

## Feasibility and Viability
Analysis of Feasibility

Technical Feasibility: High. All core components—PostGIS, OR-Tools, mobile computer vision, and UPI split-payment gateways—are mature, production-proven technologies that run smoothly on budget Android devices and standard cloud infrastructure.

Operational & Policy Feasibility: Strongly aligned with Government of India initiatives, including the 10,000 FPO Formation Scheme, e-NAM, and ONDC, which already provide institutional clustering of farmers at the village/block level.

Financial Viability: Sustainable via a low, transparent 3%–5% platform convenience and logistics orchestration fee charged primarily to B2B bulk buyers and retail orders (keeping farmer onboarding 100% free), alongside value-added services like return-haul input delivery.

Potential Challenges and Risks

Digital Literacy & Trust Deficit: Farmers may hesitate to transition away from familiar local commission agents (arhatiyas) who offer immediate cash.

Quality Disputes in Transit: Perishable produce can degrade during transit, leading to buyer rejections or payment disputes.

Cold-Chain & Rural Connectivity Gaps: Limited refrigerated transport and intermittent rural 4G connectivity can disrupt real-time operations.

Strategies for Overcoming Challenges

FPO-Assisted Onboarding & Instant Settlement: Leverage FPO managers as trusted local facilitators and release 80%–90% of payment immediately via UPI upon quality check at the FPO collection hub.

Standardized Digital Grading & Escrow: Capture timestamped, AI-graded photos at pickup and drop-off to eliminate subjective quality disputes.

Offline-First App & Micro-Reefer Pooling: Enable offline order caching with SMS fallback, and partner with existing local logistics aggregators (Porter, Blowhorn, and rural tempo unions) using insulated crates for short-haul routes.

## Impact and Benefits

Potential Impact on Target Audience

Farmers & FPOs: Gain transparent price discovery, guaranteed off-take through forward demand matching, and faster payment cycles without middleman deductions.

Consumers & Bulk Buyers: Access fresher, traceable, chemical-residue-declared produce at predictable prices with reliable doorstep or dock delivery.

Key Benefits

Economic: Increases net farmer realization by 15%–25% while reducing consumer retail prices by 10%–18% through intermediary compression and optimized freight utilization.

Social: Empowers rural FPOs as self-sustaining micro-enterprises, creates local rural employment in sorting, grading, and last-mile transport, and reduces farmer debt distress.

Environmental: Reduces post-harvest food wastage (currently 15%–30% in perishables) via demand-synced harvesting, and lowers carbon emissions per ton-kilometer through AI-consolidated milk-run routing.

## Research and References
Agmarknet (Directorate of Marketing & Inspection, Ministry of Agriculture & Farmers Welfare): Real-time mandi prices and arrival datasets used for price benchmarking and demand modeling — https://agmarknet.gov.in

Open Network for Digital Commerce (ONDC) — Agriculture Domain Specifications: Interoperable protocol standards for agri-input and produce discovery — https://ondc.org

e-NAM (National Agriculture Market): Reference framework for electronic auctioning, assaying, and quality parameters — https://enam.gov.in

Google OR-Tools — Vehicle Routing Problem (CVRPTW): Algorithmic foundation for multi-stop pickup and delivery route optimization — https://developers.google.com/optimization/routing

NABARD FPO Resource Portal & Dalwai Committee Report (Doubling Farmers' Income): Empirical data on agricultural supply chain markups, post-harvest losses, and FPO aggregation models — https://www.nabard.org
