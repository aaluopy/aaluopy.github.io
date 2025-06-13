---
layout: page
title: Collections
permalink: /collections/
---

# Collections

Welcome to my curated collections! Here you'll find organized groups of related content that dive deep into specific topics.

<div class="collections-grid">
  <div class="collection-card">
    <h3>Kubernetes Series</h3>
    <p>A comprehensive guide to Kubernetes, from basics to advanced topics including deployment strategies, networking, and best practices.</p>
    <div class="collection-meta">
      <span class="post-count">Coming Soon</span>
    </div>
  </div>
  
  <div class="collection-card">
    <h3>Prometheus Monitoring</h3>
    <p>Learn how to implement effective monitoring and alerting with Prometheus, including setup, configuration, and advanced querying.</p>
    <div class="collection-meta">
      <span class="post-count">Coming Soon</span>
    </div>
  </div>
  
  <div class="collection-card">
    <h3>Elastic Stack Deep Dive</h3>
    <p>Master the ELK stack (Elasticsearch, Logstash, Kibana) for log management, search, and data visualization.</p>
    <div class="collection-meta">
      <span class="post-count">Coming Soon</span>
    </div>
  </div>
  
  <div class="collection-card">
    <h3>DevOps Best Practices</h3>
    <p>Essential DevOps practices, tools, and methodologies for modern software development and deployment.</p>
    <div class="collection-meta">
      <span class="post-count">Coming Soon</span>
    </div>
  </div>
  
  <div class="collection-card">
    <h3>Cloud Native Journey</h3>
    <p>Navigate the cloud-native landscape with guides on containerization, microservices, and cloud platforms.</p>
    <div class="collection-meta">
      <span class="post-count">Coming Soon</span>
    </div>
  </div>
  
  <div class="collection-card">
    <h3>Infrastructure as Code</h3>
    <p>Learn to manage infrastructure using code with tools like Terraform, Ansible, and CloudFormation.</p>
    <div class="collection-meta">
      <span class="post-count">Coming Soon</span>
    </div>
  </div>
</div>

## What are Collections?

Collections are carefully curated series of posts that build upon each other to provide comprehensive coverage of specific topics. Unlike regular blog posts, collections are designed to be read in sequence and offer a structured learning path.

## How to Use Collections

1. **Choose a topic** that interests you from the grid above
2. **Start from the beginning** - collections are designed to build knowledge progressively
3. **Follow the recommended order** for the best learning experience
4. **Practice along** - many collections include hands-on examples and exercises

---

*Collections will be populated as content is published. Check back regularly for new additions!*

<style>
.collections-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  margin: 2rem 0;
}

.collection-card {
  background: white;
  border: 1px solid #e8e8e8;
  border-radius: 8px;
  padding: 2rem;
  transition: transform 0.2s, box-shadow 0.2s;
  cursor: pointer;
}

.collection-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 5px 20px rgba(0,0,0,0.1);
}

.collection-card h3 {
  margin-top: 0;
  margin-bottom: 1rem;
  color: #333;
  font-size: 1.3rem;
}

.collection-card p {
  color: #666;
  line-height: 1.6;
  margin-bottom: 1.5rem;
}

.collection-meta {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-top: 1rem;
  border-top: 1px solid #f0f0f0;
}

.post-count {
  background: #f8f9fa;
  color: #6c757d;
  padding: 0.25rem 0.75rem;
  border-radius: 12px;
  font-size: 0.85rem;
  font-weight: 500;
}

.difficulty {
  color: #28a745;
  font-weight: 500;
  font-size: 0.9rem;
}

.difficulty.intermediate {
  color: #ffc107;
}

.difficulty.advanced {
  color: #dc3545;
}

@media screen and (max-width: 600px) {
  .collections-grid {
    grid-template-columns: 1fr;
  }
  
  .collection-card {
    padding: 1.5rem;
  }
}
</style>