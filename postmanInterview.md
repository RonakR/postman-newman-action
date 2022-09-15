# Postman Interview

## Client Concerns

1. I am looking into the possibility of using Postman in my team.  From my initial investigations, it looks like the content created within my Postman team is visible and editable to anyone on the team. This is great, but concerns me from a workflow/compliance perspective.  Can you tell me how Postman handles this?
    - Postman provides **Role-Based Access Control (RBAC)** for specific and granular access to individuals. This promotes regulation on access, and separation of concerns among team members.
    - These roles can be applied to individuals at a team level, workspace level, element level, or even more granularly to APIs, Environments, Mock servers, and Monitors. 
    - Roles can be applied to groups of individuals as well, this is a feature available in the Enterprise Plan.
    - Some examples of roles at a team level include:
      - **Super Admin**: Manages high-level access to all controls within Postman
      - **Admin**: Manages access within teams
      - **Billing**: Manages team plan and payments
      - **Developer**: Has access to all team resources and workspaces
2. How can Postman help me with testing automation?
    - Testing an API is an integral part of using Postman, right after exposing an API. Postman offers 3 ways to help with testing automation: Collection Runners, Newman, and Monitors.
    - The backbone of all those automation features are Tests. Tests are written in Postman and are run right after a request is completed.
      - **Collection Runner**: is a waterfall automation of all the tests written in a Collection. This is the baseline of automation and opens doors to the other two processes.
      - **Newman**: is an open source library developed by Postman that allows programmatic execution of Collection Runners. Newman's CLI is handy when writing scripts running Collection Runners in your CI/CD pipelines.
      - **Monitors**: are a time-based form of automation, triggering at certain intervals to run selected Collection Runners. These are often used to monitor the reachability of API endpoints defined in the Collection Runner.

## Demonstration
Demonstration covering requirements below is available in the provided JSON files.
- Retrieves the weather for San Francisco, USA
- Tests to ensure the temperature is in a sensible range
- If the temperature is over 60F, retrieve the weather for Bangalore, India
- Else, retrieve the weather for London, UK

## Bonus Question

- If you'd like to show off more of your technical knowledge, then fix the following JavaScript function and provide a few sentences on what was wrong: 
  #### **Mistakes**
  - **Mistake 1**: `nums` argument is treated both as an:
    - integer in the `for-loop` definition.
    - and as an array when indexed within the `for-loop`.
  - **Mistake 2**: In Javascript, carat (`^`) is a `bitwise XOR` operator.
  #### **Fixes**
  - **Fix 1**: Treat `nums` as an array and add `.length` for accurate traversal.
  - **Fix 2**: Start `i` at `0` to account for all values in `nums` array.
  - **Fix 3**: Use either `**` or `Math.pow()` for squaring.
  
```js
function sumNumbersAndSquareResult (nums) {
    let total = 0;
    for (let i = 0; i < nums.length; i++) { // Fix 1 and 2
        total += nums[i];
    }
    return total ** 2; // Fix 3
}
```