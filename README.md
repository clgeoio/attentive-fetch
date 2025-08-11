# attentive-fetch

Attentive's API, but using native fetch

This was created using `@hey-api` specifically the command:

```
npx @hey-api/openapi-ts  \
-i ./attentive.json \
-o src  \
-c @hey-api/client-fetch
```

Example usage:

```
    import { getEvents } from 'attentive-api-fetch';

    const eventsRes = await getEvents({
      headers: {
        Authorization: `Attentive-API-Key ${attentiveApiKey}`,
        revision: '2025-01-15',
      },
      query: {
        'page[cursor]': nextPageToken ?? undefined,
        sort,
        filter: metricId ? `equals(metric_id,${metricId})` : undefined,
        include: ['metric', 'profile'],
        'fields[metric]': ['name'],
        'fields[event]': ['datetime', 'timestamp', 'event_properties'],
        'fields[profile]': ['email', 'first_name', 'last_name', 'phone_number'],
      },
    });
```
