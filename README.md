# Rating Models\nclass 
Rating(BaseModel):\n    id: str = Field(default_factory=lambda: str(uuid.uuid4()))\n    event_id: str\n    from_user_id: str\n    to_user_id: str\n    rating: int  # 1-5\n    comment: Optional[str] = None\n    created_at: datetime = Field(default_factory=datetime.utcnow) --new-str # Rating Models\nclass Rating(BaseModel):\n    id: str = Field(default_factory=lambda: str(uuid.uuid4()))\n    event_id: str\n    from_user_id: str\n    to_user_id: str\n    rating: int  # 1-5\n    comment: Optional[str] = None\n    created_at: datetime = Field(default_factory=datetime.utcnow)\n\n# Sponsor/Advertisement Models\nclass SponsorCategory(str):\n    TRAVEL = "viagem"\n    SPORTS = "esportes"\n    RESTAURANT = "restaurante"\n    ENTERTAINMENT = "entretenimento"\n    SHOPPING = "compras"\n    TECHNOLOGY = "tecnologia"\n    OTHER = "outros"\n\nclass SponsorStatus(str):\n    ACTIVE = "ativo"\n    PAUSED = "pausado"\n    INACTIVE = "inativo"\n\nclass Sponsor(BaseModel):\n    id: str = Field(default_factory=lambda: str(uuid.uuid4()))\n    name: str\n    category: str\n    logo: Optional[str] = None  # base64 image\n    website_url: str\n    contact_email: str\n    description: str\n    status: str = SponsorStatus.ACTIVE\n    created_at: datetime = Field(default_factory=datetime.utcnow)\n\nclass Advertisement(BaseModel):\n    id: str = Field(default_factory=lambda: str(uuid.uuid4()))\n    sponsor_id: str\n    title: str\n    description: str\n    image: Optional[str] = None  # base64 image\n    click_reward: float  # valor em centavos por clique\n    target_url: str\n    budget_total: float\n    budget_spent: float = 0.0\n    clicks_count: int = 0\n    status: str = SponsorStatus.ACTIVE\n    created_at: datetime = Field(default_factory=datetime.utcnow)\n    expires_at: Optional[datetime] = None\n\nclass AdClick(BaseModel):\n    id: str = Field(default_factory=lambda: str(uuid.uuid4()))\n    user_id: str\n    advertisement_id: str\n    sponsor_id: str\n    reward_amount: float\n    clicked_at: datetime = Field(default_factory=datetime.utcnow)\n\nclass SponsorCreate(BaseModel):\n    name: str\n    category: str\n    logo: Optional[str] = None\n    website_url: str\n    contact_email: str\n    description: str\n\nclass AdCreate(BaseModel):\n    sponsor_id: str\n    title: str\n    description: str\n    image: Optional[str] = None\n    click_reward: float\n    target_url: str\n    budget_total: float\n    expires_at: Optional[datetime] = None'
Observation: Edit was successful.

Fetching debug logs for expo

==> /var/log/supervisor/expo.err.log <==
    at call (/app/frontend/node_modules/connect/index.js:239:7)
    at next (/app/frontend/node_modules/connect/index.js:183:5)
    at /app/frontend/node_modules/@expo/cli/src/start/server/middleware/ContextModuleSourceMapsMiddleware.ts:29:7
    at call (/app/frontend/node_modules/connect/index.js:239:7)
    at next (/app/frontend/node_modules/connect/index.js:183:5)
    at ExpoGoManifestHandlerMiddleware.checkBrowserRequestAsync (/app/frontend/node_modules/@expo/cli/src/start/server/middleware/ManifestMiddleware.ts:366:11)
    at ExpoGoManifestHandlerMiddleware.handleRequestAsync (/app/frontend/node_modules/@expo/cli/src/start/server/middleware/ManifestMiddleware.ts:383:20)
    at internalMiddleware (/app/frontend/node_modules/@expo/cli/src/start/server/middleware/ExpoMiddleware.ts:44:27)
    at middleware (/app/frontend/node_modules/@expo/cli/src/start/server/middleware/ExpoMiddleware.ts:64:14)
Error: Unauthorized request from https://app.emergent.sh. This may happen because of a conflicting browser extension to intercept HTTP requests. Disable browser extensions or use incognito mode and try again.
    at /app/frontend/node_modules/@expo/cli/src/start/server/middleware/CorsMiddleware.ts:27:11
    at call (/app/frontend/node_modules/connect/index.js:239:7)
    at next (/app/frontend/node_modules/connect/index.js:183:5)
    at /app/frontend/node_modules/@expo/cli/src/start/server/middleware/ContextModuleSourceMapsMiddleware.ts:29:7
    at call (/app/frontend/node_modules/connect/index.js:239:7)
    at next (/app/frontend/node_modules/connect/index.js:183:5)
    at ExpoGoManifestHandlerMiddleware.checkBrowserRequestAsync (/app/frontend/node_modules/@expo/cli/src/start/server/middleware/ManifestMiddleware.ts:366:11)
    at ExpoGoManifestHandlerMiddleware.handleRequestAsync (/app/frontend/node_modules/@expo/cli/src/start/server/middleware/ManifestMiddleware.ts:383:20)
    at internalMiddleware (/app/frontend/node_modules/@expo/cli/src/start/server/middleware/ExpoMiddleware.ts:44:27)
    at middleware (/app/frontend/node_modules/@expo/cli/src/start/server/middleware/ExpoMiddleware.ts:64:14)

==> /var/log/supervisor/expo.out.log <==
 LOG  [web] Logs will appear in the browser console
 LOG  [web] Logs will appear in the browser console
Web node_modules/expo-router/entry.js ░░░░░░░░░░░░░░░░  0.0% (0/1)
λ Bundled 45ms node_modules/expo-router/node/render.js (1 module)
Web Bundled 407ms node_modules/expo-router/entry.js (1 module)
Web Bundled 34ms node_modules/expo-router/entry.js (1 module)
 LOG  [web] Logs will appear in the browser console
 LOG  [web] Logs will appear in the browser console
Web node_modules/expo-router/entry.js ░░░░░░░░░░░░░░░░  0.0% (0/1)
λ Bundled 32ms node_modules/expo-router/node/render.js (1 module)
Web Bundled 317ms node_modules/expo-router/entry.js (1 module)
Web Bundled 31ms node_modules/expo-router/entry.js (1 module)
 LOG  [web] Logs will appear in the browser console
 LOG  [web] Logs will appear in the browser console
Web node_modules/expo-router/entry.js ░░░░░░░░░░░░░░░░  0.0% (0/1)
λ Bundled 47ms node_modules/expo-router/node/render.js (1 module)
Web Bundled 375ms node_modules/expo-router/entry.js (1 module)
Web Bundled 33ms node_modules/expo-router/entry.js (1 module)
 LOG  [web] Logs will appear in the browser console
 LOG  [web] Logs will appear in the browser console


Fetching debug logs for backend

==> /var/log/supervisor/backend.err.log <==
INFO:     Shutting down
INFO:     Waiting for application shutdown.
INFO:     Application shutdown complete.
INFO:     Finished server process [1748]
INFO:     Started server process [1839]
INFO:     Waiting for application startup.
INFO:     Application startup complete.
WARNING:  WatchFiles detected changes in 'server.py'. Reloading...
INFO:     Shutting down
INFO:     Waiting for application shutdown.
INFO:     Application shutdown complete.
INFO:     Finished server process [1839]
INFO:     Started server process [1918]
INFO:     Waiting for application startup.
INFO:     Application startup complete.
WARNING:  WatchFiles detected changes in 'server.py'. Reloading...
INFO:     Shutting down
INFO:     Waiting for application shutdown.
INFO:     Application shutdown complete.
INFO:     Finished server process [1918]

==> /var/log/supervisor/backend.out.log <==
INFO:     10.64.136.132:47592 - "POST /api/events/e7f64ea9-0c42-4e8f-b38d-b42a0efdeef4/apply HTTP/1.1" 403 Forbidden
INFO:     10.64.135.173:59214 - "POST /api/register HTTP/1.1" 400 Bad Request
INFO:     10.64.133.112:50136 - "POST /api/register HTTP/1.1" 400 Bad Request
INFO:     10.64.133.112:57800 - "POST /api/register HTTP/1.1" 400 Bad Request
INFO:     10.64.133.112:33518 - "POST /api/register HTTP/1.1" 400 Bad Request
INFO:     10.64.134.61:55898 - "POST /api/register HTTP/1.1" 400 Bad Request
INFO:     10.64.134.61:55898 - "POST /api/register HTTP/1.1" 400 Bad Request
INFO:     10.64.138.97:41604 - "POST /api/register HTTP/1.1" 400 Bad Request
INFO:     10.64.141.204:56358 - "POST /api/register HTTP/1.1" 400 Bad Request
INFO:     10.64.168.87:56380 - "POST /api/register HTTP/1.1" 400 Bad Request
INFO:     10.64.141.204:40858 - "POST /api/register HTTP/1.1" 400 Bad Request
INFO:     10.64.141.204:40858 - "POST /api/register HTTP/1.1" 400 Bad Request
INFO:     10.64.168.87:40744 - "POST /api/register HTTP/1.1" 400 Bad Request
INFO:     10.64.168.87:40744 - "POST /api/register HTTP/1.1" 400 Bad Request
INFO:     10.64.141.204:40858 - "POST /api/register HTTP/1.1" 400 Bad Request
INFO:     10.64.168.87:40744 - "POST /api/register HTTP/1.1" 400 Bad Request
INFO:     10.64.168.87:40744 - "POST /api/register HTTP/1.1" 400 Bad Request
INFO:     10.64.136.132:38296 - "POST /api/register HTTP/1.1" 400 Bad Request
INFO:     10.64.168.87:40744 - "POST /api/register HTTP/1.1" 400 Bad Request
INFO:     10.64.141.204:58574 - "POST /api/register HTTP/1.1" 400 Bad Request


Fetching debug logs for mongodb

tail: cannot open '/var/log/supervisor/mongodb*.log' for reading: No such file or directory
