This package includes a minimal /public site so Netlify can deploy successfully,
plus serverless functions for Cronofy connect/callback/events.

After deploy, test:
  /.netlify/functions/events?family=test&tzid=America/Chicago
  /.netlify/functions/connect?family=sharma&user=kota
