---
description: Endpoint for getting Guardians info.
---

# /guardian

{% swagger method="get" path="guardian/" baseUrl="https://api.umva.tk/" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="guardian_id" required="true" %}
ID of Guardian
{% endswagger-parameter %}

{% swagger-parameter in="query" name="tier" required="true" %}
Tier of Guardian
{% endswagger-parameter %}

{% swagger-parameter in="query" name="astral" %}
Astral Rating of Guardian if accessing 5* tier data
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Successful response" %}
Example for **https://api.umva.tk/guardian/?guardian\_id=belle\&tier=5\&astral=3**

```javascript
{
    "name": "Belle",
    "id": "belle",
    "catchline": "Explorer mage",
    "type": "Support",
    "rarity": 5,
    "astral_rating": 3,
    "img_url": "https://disneymirrorverse.com/wp-content/uploads/portraits/portrait-belle.png",
    "health": 4985,
    "attack": 3629,
    "defense": 4013,
    "focus": 5451,
    "abilities": [
        {
            "name": "Enchanting Defense",
            "type": "Core",
            "info": [
                "At the beginning of each combat, Belle grants all allies a 10% Defense Buff for the duration of the encounter."
            ],
            "image_url": "https://disneymirrorverse.com/wp-content/uploads/cores/belle_core_ability.jpg"
        },
        {
            "name": "Healing Bloom",
            "type": "Special",
            "info": [
                "All allies Heal 2.5% each second for 4 seconds. (Max Stacks: 1)",
                "Belle has a 15% chance to additionally grant 10% Armor to all allies."
            ],
            "image_url": "https://disneymirrorverse.com/wp-content/uploads/specials/belle_special.jpg"
        },
        {
            "name": "Nature'S Spell",
            "type": "Signature",
            "info": [
                "Belle’s Special Ability gains an additional 35% chance to grant Armor to allies."
            ],
            "image_url": "https://disneymirrorverse.com/wp-content/uploads/signatures/belle_sig.jpg"
        }
    ],
    "talents": [
        {
            "name": "Nature's Voice",
            "image_url": "https://disneymirrorverse.com/wp-content/uploads/talents/reflections_belle_philippe.png",
            "type": "BASIC",
            "max_level": "LEVEL 12",
            "info": "Grants +20% Health at the start of an encounter."
        },
        {
            "name": "Forgotten Knowledge",
            "image_url": "https://disneymirrorverse.com/wp-content/uploads/talents/reflections_belle_sheep.png",
            "type": "BASIC",
            "max_level": "LEVEL 15",
            "info": "Grants +20% Focus at the start of an encounter."
        },
        {
            "name": "Healer’s Touch",
            "image_url": "https://disneymirrorverse.com/wp-content/uploads/talents/reflections_belle_cogsw.png",
            "type": "ADVANCED",
            "max_level": "LEVEL 20",
            "info": "Heals from Belle are 40% stronger."
        },
        {
            "name": "Enchantment Enhancement",
            "image_url": "https://disneymirrorverse.com/wp-content/uploads/talents/reflections_belle_maurice.png",
            "type": "ADVANCED",
            "max_level": "LEVEL 20",
            "info": "Whenever Belle activates a Heal on an ally, that ally gains a 10% Defense Buff for 10 seconds."
        },
        {
            "name": "Active Growth",
            "image_url": "https://disneymirrorverse.com/wp-content/uploads/talents/reflections_belle_lumiere.png",
            "type": "ADVANCED",
            "max_level": "LEVEL 25",
            "info": "When Belle’s Core Ability activates, all allies gain 15% Armor."
        },
        {
            "name": "Reflexive Restoration",
            "image_url": "https://disneymirrorverse.com/wp-content/uploads/talents/reflections_belle_potts.png",
            "type": "ELITE",
            "max_level": "LEVEL 30",
            "info": "When Belle’s Core Ability activates, all allies also Heal 3.5% each second for 4 seconds. Belle’s Core Ability will activate during combat when a teammate reaches 10% HP. This effect will only activate once per encounter for each teammate."
        }
    ],
    "status": 200,
    "detail": "Successful"
}
```
{% endswagger-response %}

{% swagger-response status="404: Not Found" description="Wrong guardian_id/Invalid Tier" %}
Example for **https://api.umva.tk/guardian/?guardian\_id=belle\&tier=7\&astral=3**

(Note: You'll notice the `tier` parameter is more than 5.)

```javascript
{
    "detail": "Tier of guardian cannot be more than 5"
}
```

Example for **https://api.umva.tk/guardian/?guardian\_id=xd\&tier=7\&astral=3**

(Note: You'll notice the `guardian_id` parameter is not a valid name for a guardian name.)

```javascript
{
    "detail": "'xD' is not a valid Guardian ID."
}
```
{% endswagger-response %}

{% swagger-response status="422: Unprocessable Entity" description="Missing param/ Invalid param" %}
Example for **https://api.umva.tk/guardian/?guardian\_id=belle\&astral=3**

(Note: You'll notice the `tier` parameter is missing.)

```javascript
{
    "detail": "The following arguments are missing/invalid: tier"
}
```
{% endswagger-response %}
{% endswagger %}
