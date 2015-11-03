# newsletter-subscription
Polymer web component. Minimalist library for newsletter subscription. No jQuery.

## Install

Install the component using [Bower](http://bower.io/):

```sh
$ bower install newsletter-subscription --save
```

Or [download as ZIP](https://github.com/kilombo/newsletter-subscription/archive/master.zip).

## Usage

1. Import Polymer Library:

    ```html
    <link rel="import" bower_components/polymer/polymer.html">
    ```

2. Import Web Components' polyfill:

    ```html
    <script src="bower_components/webcomponentsjs/webcomponents.js"></script>
    ```

3. Import Custom Element:

    ```html
    <link rel="import" href="bower_components/newsletter-subscription/twitter-button.html">
    ```

3. Start using it!

    ```html
    <paper-button data-dialog="scrolling" onclick="clickHandler(event)">Newsletter</paper-button>
    <newsletter-subscription id="newsletter-subscription">
        <h2>My Newsletter</h2>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
    </newsletter-subscription>
    <script>
        function clickHandler(e) {
            var button = e.target;
            while (!button.hasAttribute('data-dialog') && button !== document.body) {
                button = button.parentElement;
            }

            if (!button.hasAttribute('data-dialog')) {
                return;
            }

            var id = button.getAttribute('data-dialog');
            var dialog = document.getElementById(id);
            if (dialog) {
                dialog.open();
            }
        }
    </script>
    ```
4. You can hide the buttons
    ```html
    <newsletter-subscription id="newsletter-subscription" hide-buttons></newsletter-subscription>
    ```


## Development

In order to run it locally you'll need to fetch some dependencies and a basic server setup.

* Install [Bower](http://bower.io/) & [Grunt](http://gruntjs.com/):

    ```sh
    $ [sudo] npm install -g bower grunt-cli
    ```

* Install local dependencies:

    ```sh
    $ bower install && npm install
    ```

* To test your project, start the development server and open `http://localhost:8000`.

    ```sh
    $ grunt server
    ```

* To build the distribution files before releasing a new version.

    ```sh
    $ grunt build
    ```

* To provide a live demo, send everything to `gh-pages` branch.

    ```sh
    $ grunt deploy
    ```

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -m 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## History

For detailed changelog, check [Releases](https://github.com/kilombo/newsletter-subscription/releases).