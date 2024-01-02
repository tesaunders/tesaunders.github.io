---
title: "Projects"
date: 2023-01-03T10:24:00+13:00
draft: false
hideMeta: true
---

<script>
  const username = 'tesaunders';
  const apiUrl = `https://api.github.com/users/${username}/repos`;

  // Function to fetch repositories from GitHub API
  async function fetchRepositories() {
    try {
      const response = await fetch(apiUrl);
      const repos = await response.json();
      return repos;
    } catch (error) {
      console.error('Error fetching repositories:', error);
      return [];
    }
  }

  // Function to filter repositories with a URL
  function filterReposWithUrl(repos) {
    return repos.filter(repo => repo.homepage && repo.homepage != "http://tomsaunders.me/rstudio-pubs/");
  }

  // Function to generate iframes for each URL
  function generateIframes(repos) {
    const postContent = document.querySelector('.post-content');

    repos.forEach(repo => {
      const iframe = document.createElement('iframe');
      iframe.src = repo.homepage;
      iframe.width = '100%';
      iframe.height = '400px';
      postContent.appendChild(iframe);
    });
  }

  // Fetch repositories, filter with URL, and generate iframes
  fetchRepositories()
    .then(filterReposWithUrl)
    .then(generateIframes);
</script>