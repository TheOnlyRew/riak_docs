---
title: HTTP API
project: riak
version: 1.0.0+
document: api
toc: true
audience: advanced
keywords: [api, http]
index: true
moved: {
  '1.4.0-': '/references/apis/http'
}
---

Riak has a rich, full-featured HTTP 1.1 API. This is an overview of the
operations you can perform via HTTP and can be used as a guide for
developing a compliant client. All URLs assume the default configuration
values where applicable. All examples use `curl` to interact with Riak.

<div class="note">
<div class="title">URL Escaping</div>
Buckets, keys, and link specifications may not contain unescaped
slashes. Use a URL-escaping library or replace slashes with `%2F`.
</div>

## Bucket-related Operations

Method | URL | Doc
:------|:----|:---
`GET` | `/types/<type>/buckets/<bucket>/props` | [[HTTP Get Bucket Properties]]
`PUT` | `/types/<type>/buckets/<bucket>/props` | [[HTTP Set Bucket Properties]]
`DELETE` | `/types/<type>/buckets/<bucket>/props` | [[HTTP Reset Bucket Properties]]
`GET` | `/types/<type>/buckets?buckets=true` | [[HTTP List Buckets]]
`GET` | `/types/<type>/buckets/<bucket>/keys?keys=true` | [[HTTP List Keys]]

## Object-related Operations

Method | URL | Doc
:------|:----|:---
`GET` | `/types/<type>/buckets/<bucket>/keys/<key>` | [[HTTP Fetch Object]]
`POST` | `/types/<type>/buckets/<bucket>/keys/<key>` | [[HTTP Store Object]]
`PUT` | `/types/<type>/buckets/<bucket>/keys/<key>` | [[HTTP Store Object]]
`DELETE` | `/types/<type>/buckets/<bucket>/keys/<key>` | [[HTTP Delete Object]]

## Riak-Data-Type-related Operations

For documentation on the HTTP API for [[Riak Data Types|Data Types]],
see the `curl` examples in [[Using Data Types]].

## Query-related Operations

Method | URL | Doc
:------|:----|:---
`POST` | `/mapred` | [[HTTP MapReduce]]
`GET` | `/types/<type>/buckets/<bucket>/index/<index>/<value>` | [[HTTP Secondary Indexes]]
`GET` | `/types/<type>/buckets/<bucket>/index/<index>/<start>/<end>` | [[HTTP Secondary Indexes]]

## Server-related Operations

Method | URL | Doc
:------|:----|:---
`GET` | `/ping` | [[HTTP Ping]]
`GET` | `/stats` | [[HTTP Status]]
`GET` | `/` | [[HTTP List Resources]]

## Search-related Operations

Method | URL | Doc
:------|:----|:---
`GET` | `/search/query/<index_name>` | [[HTTP Search Query]]
`GET` | `/search/index` | [[HTTP Search Index Info]]
`GET` | `/search/index/<index_name>` | [[HTTP Fetch Search Index]]
`PUT` | `/search/index/<index_name>` | [[HTTP Store Search Index]]
`DELETE` | `/search/index/<index_name>` | [[HTTP Delete Search Index]]
`GET` | `/search/schema/<schema_name>` | [[HTTP Fetch Search Schema]]
`PUT` | `/search/schema/<schema_name>` | [[HTTP Store Search Schema]]
