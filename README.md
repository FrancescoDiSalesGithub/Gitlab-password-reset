# Gitlab-password-reset
operation for resetting gitlab root password

# How to reset root password in gitlab

Considering that the user is logged in as root user, run **gitlab-rails**:
```

gitlab-rails console

```
Wait until gitlab-rails gives you informations about the gitlab instance. Then run the following snippet:
```
user = User.where(id: 1).first
user.password = 'new_password'
user.password_confirmation = 'new_password'
user.save
exit
```

Then restart the gitlab service:
```
sudo gitlab-ctl restart
```

Wait for gitlab to restart its component and then go to the gitlab login page. and write the following credentials:
```
root:new_password
```

If the steps are correct you should login with the password that was inserted in the gitlab-rails console.

# Donation
If you have found this guide interesting please donate me some monero coins at:
```
4B9WQivaHfd3miDfPKEfCianocGpBx9d8FXycz2vmNW3aBDVKHgkBd9Gmapt4RBVEpTwnehujsiUBBehUiLvnEHs7VFstCC
```
If you can't donate me monero coins, you can still apply to the academy hack the box website here:
```
https://referral.hackthebox.com/mzwyliz
```
