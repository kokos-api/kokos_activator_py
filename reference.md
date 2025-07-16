# Reference
## Database
<details><summary><code>client.database.<a href="src/kokos_activator_api/database/client.py">get_inventory</a>()</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get the amount of codes in the database for each pack
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from kokos_activator_api import KokosApi
from kokos_activator_api.environment import KokosApiEnvironment

client = KokosApi(
    token="YOUR_TOKEN",
    environment=KokosApiEnvironment.PRODUCTION,
)
client.database.get_inventory()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.database.<a href="src/kokos_activator_api/database/client.py">upload_codes</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Add codes to the database
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from kokos_activator_api import KokosApi
from kokos_activator_api.database import UploadPack
from kokos_activator_api.environment import KokosApiEnvironment

client = KokosApi(
    token="YOUR_TOKEN",
    environment=KokosApiEnvironment.PRODUCTION,
)
client.database.upload_codes(
    request=[
        UploadPack(
            denomination=60,
            codes=[
                "r3h4x2Jh2W2853g9g4",
                "Nq7QDWZw2F2eZ4ndZd",
                "Nq7QDHZA2Q2cZ7rdw3",
                "Nq7QDYZa2N22Z0r0vc",
                "Nq7QDDZ72U4738E64c",
            ],
        )
    ],
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `typing.Sequence[UploadPack]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.database.<a href="src/kokos_activator_api/database/client.py">download_codes</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Extract codes from the database
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from kokos_activator_api import KokosApi
from kokos_activator_api.environment import KokosApiEnvironment

client = KokosApi(
    token="YOUR_TOKEN",
    environment=KokosApiEnvironment.PRODUCTION,
)
client.database.download_codes(
    denomination=60,
    amount=5,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**denomination:** `PackDenomination` 
    
</dd>
</dl>

<dl>
<dd>

**amount:** `int` — Amount of codes to extract
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## History
<details><summary><code>client.history.<a href="src/kokos_activator_api/history/client.py">get_stats</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get statistics about the number of redemptions for each pack on a given date. `0` in the `activations` field means that the activation was successful, but was performed with `codeOverride` and `requireReceipt` set to `false`, and so the amount is unknown. `0` in the `errors` field means that the activation was unsuccessful, and the amount is unknown.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
import datetime

from kokos_activator_api import KokosApi
from kokos_activator_api.environment import KokosApiEnvironment

client = KokosApi(
    token="YOUR_TOKEN",
    environment=KokosApiEnvironment.PRODUCTION,
)
client.history.get_stats(
    date=datetime.date.fromisoformat(
        "2025-05-12",
    ),
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**date:** `typing.Optional[dt.date]` — The date to get statistics for. Defaults to the current date.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.history.<a href="src/kokos_activator_api/history/client.py">get_activation_history</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get the list of recent activations
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from kokos_activator_api import KokosApi
from kokos_activator_api.environment import KokosApiEnvironment

client = KokosApi(
    token="YOUR_TOKEN",
    environment=KokosApiEnvironment.PRODUCTION,
)
client.history.get_activation_history()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**before:** `typing.Optional[dt.datetime]` — Get activations before this timestamp (sorted newest first)
    
</dd>
</dl>

<dl>
<dd>

**after:** `typing.Optional[dt.datetime]` — Get activations after this timestamp (sorted oldest first)
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.history.<a href="src/kokos_activator_api/history/client.py">get_receipt</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get the full receipt for an existing activation
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from kokos_activator_api import KokosApi
from kokos_activator_api.environment import KokosApiEnvironment

client = KokosApi(
    token="YOUR_TOKEN",
    environment=KokosApiEnvironment.PRODUCTION,
)
client.history.get_receipt(
    id=100407,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Activation ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Redeem
<details><summary><code>client.redeem.<a href="src/kokos_activator_api/redeem/client.py">redeem_code</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Activate a code
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from kokos_activator_api import KokosApi
from kokos_activator_api.environment import KokosApiEnvironment
from kokos_activator_api.redeem import RedeemCodeFromDbRequest

client = KokosApi(
    token="YOUR_TOKEN",
    environment=KokosApiEnvironment.PRODUCTION,
)
client.redeem.redeem_code(
    request=RedeemCodeFromDbRequest(
        require_receipt=True,
        player_id="51709255708",
        denomination=660,
    ),
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `RedeemCodeRequest` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.redeem.<a href="src/kokos_activator_api/redeem/client.py">get_redemption_time</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get the redemption time of a code
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from kokos_activator_api import KokosApi
from kokos_activator_api.environment import KokosApiEnvironment

client = KokosApi(
    token="YOUR_TOKEN",
    environment=KokosApiEnvironment.PRODUCTION,
)
client.redeem.get_redemption_time(
    code="r3h4xcJ72f2056g7h7",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**code:** `Code` — Code to check
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.redeem.<a href="src/kokos_activator_api/redeem/client.py">get_character</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get information about a player
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from kokos_activator_api import KokosApi
from kokos_activator_api.environment import KokosApiEnvironment

client = KokosApi(
    token="YOUR_TOKEN",
    environment=KokosApiEnvironment.PRODUCTION,
)
client.redeem.get_character(
    player_id="51709255708",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**player_id:** `PlayerId` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

