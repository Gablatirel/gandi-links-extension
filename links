(function(Gandi) {
  class LinksExtension {
    getInfo() {
      return {
        id: 'links',
        name: 'Links',
        color1: '#3366cc',
        blocks: [
          {
            opcode: 'redirectToWebsite',
            blockType: Gandi.BlockType.COMMAND,
            text: 'redirect to [URL]',
            arguments: {
              URL: {
                type: Gandi.ArgumentType.STRING,
                defaultValue: 'https://example.com'
              }
            }
          },
          {
            opcode: 'isWebsite',
            blockType: Gandi.BlockType.BOOLEAN,
            text: 'is website [URL]?',
            arguments: {
              URL: {
                type: Gandi.ArgumentType.STRING,
                defaultValue: 'https://example.com'
              }
            }
          },
          {
            opcode: 'getWebsiteVariable',
            blockType: Gandi.BlockType.REPORTER,
            text: 'website'
          }
        ]
      };
    }

    constructor() {
      this.website = 'https://example.com';
    }

    redirectToWebsite(args) {
      const url = args.URL;
      this.website = url;
      window.location.href = url;
    }

    isWebsite(args) {
      const url = args.URL;
      try {
        new URL(url); // Checks if it's a valid URL format
        return true;
      } catch (e) {
        return false;
      }
    }

    getWebsiteVariable() {
      return this.website;
    }
  }

  Gandi.extensions.register(new LinksExtension());
})(Gandi);
