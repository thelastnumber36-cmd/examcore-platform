Di sinilah semua modul utama didefinisikan.
Web App

│

├── Identity

├── Dashboard

├── Question Bank

├── Exam

├── Assessment

├── Certificate

├── Analytics

└── System

Setiap modul nantinya memiliki:
Feature

↓

Components

↓

Hooks

↓

Services

↓

Repository

↓

Supabase

Ini adalah aturan wajib. Komponen React tidak boleh mengakses Supabase secara langsung. Semua akses data harus melalui layer services atau repository agar logika bisnis tetap terpusat dan mudah diuji.