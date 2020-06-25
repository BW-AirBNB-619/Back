# how to login with oauth2 for my boy troy
Authenticating with OAUTH2 is similar to JWT as both return a token upon success. The main difference is the header and url path.

Existing users admin/password, cinnamon/1234567

Example login Request:
axios.post('https://medcabinetjune2020.herokuapp.com/login', 
    `grant_type=password&username=${this.state.username}&password=${this.state.password}`, 
    {
        headers: {
            // btoa is converting our client id/client secret into base64
            Authorization: `Basic ${btoa('lambda-client:lambda-secret')}`,
            'Content-Type': 'application/x-www-form-urlencoded'
        }
    }
)
