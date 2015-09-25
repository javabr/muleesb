#README

This example show how tricky variable scopes can be. 

If a public flow calls a subflow all session vars and flow vars created on the primary caller flow will be visible both in the subflow and in the same primary caller once it returns back from the subflow.

If a public flow calls a assync public flow then all variables created in the primary public flow will be visible on the flow called but the opposite is not true (i.e. variables and sessions won't be visible on the caller flow once the call returns because the flow called was in another thread).

If you have  assync flows running in parallel (in another thread poll) then other flows won't be able to read any session variables created by such assync flows.

