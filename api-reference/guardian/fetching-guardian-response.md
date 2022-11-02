---
description: How to use guardian endpoint
---

# Fetching Guardian response

The `/guardian` endpoint requires 3 query params- `guardian_id` ,`tier` and `astral`(Optional). \
For example, if you want to get info about **tier 5 Ariel of astral 10**, the URL will be `https://api.umva.tk/guardian/?guardian_id=ariel&tier=5&astral=10`

### Guardian IDs

To make searching the guardians minimal, we have used guardian IDs which allow you to search them. They are very much similar to the real name of the guardians.

#### Why Guardian IDs and not Names?

Let's take **Cruella De Vil** for example, As you see her name includes spaces and accessing her data using that as the parameter would be a little tricky. So, we used `guardian_id` which for that guardian will be `cruella-de-vil` which is better for accessing them.

#### Where to find Guardian IDs

The guardian Ids can be found [here](../../important-info/guardian-ids.md). To use, look for the guardian you would like to search and find it's corresponding ID. This ID will be used in the `guardian_id` parameter.&#x20;

### Astral Rating

Astral Rating includes ratings from 1 to 10 which can be applied on to tier 5 guardians.

**Note:** As, Astral Rating are only available for 5\* tier guardians, We have made it so that adding the `astral` parameter would only work when accessing 5\* tier of guardians and not any else.
