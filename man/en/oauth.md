# OAuth Configuration

Starting from Blessing Skin v5, we provide third-party login functionality based on OAuth2 and implement it as a plugin. With these plugins, your users do not need to register or enter a password to log in, but use their accounts on other websites or platforms to directly access the skin station.

## Basic

First, install the "OAuth Client Core" plugin in the plugin market. All third-party login functions depend on this plugin.

## Microsoft Live

### Register the app

Open [Microsoft Azure](https://portal.azure.com/), click "More Services":

![Screenshot_20200713_143515.png](https://i.loli.net/2020/07/13/IkhcFadqiUrfYPQ.png)

Then search for "App Registration" and click to enter:

![Screenshot_20200713_143629.png](https://i.loli.net/2020/07/13/HeAyG3sv89MR1Wo.png)

Click "Register Application" on the page:

![Screenshot_20200713_143909.png](https://i.loli.net/2020/07/13/lrxyMtE7Qob3Jc2.png)

Then fill in the Name and Redirect URI:

![Screenshot_20200713_144118.png](https://i.loli.net/2020/07/13/9ngb7k3wtrDT5zc.png)

"Name" can be filled in as your skin site name; "Redirect URI" is to modify the domain name according to your skin site address, but the `/auth/login/live/callback` does not need to be changed.

After filling in, click the "Register" button at the bottom of the page and wait for a while. After the registration is complete, you will get the "Application (Client) ID" and copy it.

![Screenshot_20200713_150328.png](https://i.loli.net/2020/07/13/BPEOTpHVNb1WLus.png)

### create password

On the page that follows, select Certificates and Passwords on the left side of the page, and click + New Client Password.

![Screenshot_20200713_144850.png](https://i.loli.net/2020/07/13/2i3G8MmSK97JhoY.png)

In the form, set the "Deadline" to "Never", and the "Description" can be filled or not filled:

![Screenshot_20200713_144921.png](https://i.loli.net/2020/07/13/ZET6qkRWObvmlFu.png)

Then click "Add". At this point you will get the "client secret":

![Screenshot_20200713_150805.png](https://i.loli.net/2020/07/13/OtTxNumLY91cpnb.png)

**NOTE**: This password will only appear once, so it must be copied.

### Install plugin

Enter the plugin market of Blessing Skin, download, install and open the "Sign in with Microsoft Live" plugin.

### Configure the plugin

Configuration of plugins is done by modifying the `.env` file. Add the following three configurations to the `.env` file:

- `LIVE_KEY` - application (client) ID (automatically generated by Azure when registering)

- `LIVE_SECRET` - client secret (we already added one earlier)

- `LIVE_REDIRECT_URI` - the same as the "Redirect URI" we filled in when registering the app

According to the results of our previous operations, it can be filled in like this: (please modify it according to your actual situation)

````
LIVE_KEY=f53c3e81-5973-408d-80cd-e603c91caa34
LIVE_SECRET=uC00c-GnlIF199Nw34-K_A~T6sWQmQnW-S
LIVE_REDIRECT_URI=https://localhost/auth/login/live/callback
````

### Finish

When users register or log in, they can choose "Microsoft Live" to log in:

![Screenshot_20200713_151132.png](https://i.loli.net/2020/07/13/F3TQZ1tGVsImgWD.png)

![Screenshot_20200713_151158.png](https://i.loli.net/2020/07/13/xAXh3JLmZwnv1cz.png)

## LittleSkin

### Create application

In the "User Center" click "OAuth2 Application" under the "Advanced Features" menu:

![Screenshot_20200713_152743.png](https://i.loli.net/2020/07/13/AoHYj1ngkGzVMdu.png)

Click the Create App button and fill out the form:

![Screenshot_20200713_152904.png](https://i.loli.net/2020/07/13/4GphFc7WC6rwn8U.png)

The "application name" can be filled with the name of your skin station; the "callback URL" is to modify the domain name according to your skin station address, but the following `/auth/login/littleskin/callback` does not need to be changed.

Click "OK", and then you can see the application you just created:

![Screenshot_20200713_153303.png](https://i.loli.net/2020/07/13/edpgfMz9CnqLJGy.png)

### Install plugin

Enter the plugin market of Blessing Skin, download, install and open the "Sign in with LittleSkin" plugin.

### Configure the plugin

Configuration of plugins is done by modifying the `.env` file. Add the following three configurations to the `.env` file:

- `LITTLESKIN_KEY` - Client ID
- `LITTLESKIN_SECRET` - Client Secret
- `LITTLESKIN_REDIRECT_URI` - callback URL

According to the results of our previous operations, it can be filled in like this: (please modify it according to your actual situation)

````
LITTLESKIN_KEY=53
LITTLESKIN_SECRET=bgkA4FJy8biGPX33XYMhbbhAIgXHwNhUNvFg6whU
LITTLESKIN_REDIRECT_URI=https://localhost/auth/login/littleskin/callback
````

### Finish

When users register or log in, they can select "LittleSkin" to log in:

![Screenshot_20200713_174959.png](https://i.loli.net/2020/07/13/esklFQ3MngJVEpa.png)

![Screenshot_20200713_175019.png](https://i.loli.net/2020/07/13/WqEN9c34yXZbCrL.png)

## GitHub

### Register the app

Open GitHub, go to the settings page, and click "Developer settings" in the left column:

![Screenshot_20200713_180312.png](https://i.loli.net/2020/07/13/XadcJiyp9TlvC8R.png)

Click on "OAuth Apps" in the left column on the following page:

![Screenshot_20200713_180406.png](https://i.loli.net/2020/07/13/fNKvULY1ijC7dZ2.png)

Click "Register a new application" and fill out the form:

![Screenshot_20200713_180644.png](https://i.loli.net/2020/07/13/t5KRSWIvjw4gu3n.png)

Among them, "Application name" is the name of your skin site; "Homepage URL" is the home page URL of your skin site; "Authorization callback URL" is to modify the domain name according to your skin site address, but the `/auth/ login/github/callback` does not need to be changed.

Click "Register application" to continue. At this point you will get the Client ID and Client Secret:

![Screenshot_20200713_180923.png](https://i.loli.net/2020/07/13/jxz5ZYhiIPfvgqe.png)

### Install plugin

Enter the plugin market of Blessing Skin, download, install and open the "Sign in with GitHub" plugin.

### Configure the plugin

Configuration of plugins is done by modifying the `.env` file. Add the following three configurations to the `.env` file:

- `GITHUB_KEY` - corresponds to the "Client ID" provided by GitHub
- `GITHUB_SECRET` - corresponds to the "Client Secret" provided by GitHub
- `GITHUB_REDIRECT_URI` - corresponds to the "Authorization callback URL" we just filled in

According to the results of our previous operations, it can be filled in like this: (please modify it according to your actual situation)

````
GITHUB_KEY=44551e99fbe2ad35d411
GITHUB_SECRET=65409736106e5fb47eace316dc1b62309f580e47
GITHUB_REDIRECT_URI=https://localhost/auth/login/github/callback
````

### Finish

When users register or log in, they can select "GitHub" to log in:

![Screenshot_20200713_181510.png](https://i.loli.net/2020/07/13/HG4d6oacFrk5hgD.png)

![Screenshot_20200713_183554.png](https://i.loli.net/2020/07/13/Ci8qelT3cUFOZKm.png)