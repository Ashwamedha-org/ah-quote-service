Role: The heavily scaled, stateless API that processes the complex actuarial calculations and temporary quote building.

Key PoC Features:

    Redis Session Store: Holds the in-progress quote cart. If a Kubernetes pod dies, the next pod picks up the session from Redis.

    Redis Read-Aside Cache: Caches the static A&H rate tables so actuarial lookups don't hit the database.
