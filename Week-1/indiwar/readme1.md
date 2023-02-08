When a user enters an URL in the browser, how does the browser fetch the desiredresult ? Explain this with the below in mind and Demonstrate this by drawing a diagramfor the same.

On typing a URL in the browser and pressing 'Enter', the following takes place.
- Browser looks up IP address for the domain by going through the following 4 layers.
  -- Browser cache is check to find the IP address of recently visited sites.
  -- OS cache is checked
  -- Router cache is checked. No joy, then request sends to top or root server of the DNS hierarchy.
  -- Resolver server (of the Internet Service Provider) is checked based on the input from the result from Router cache for different URLs eg .com, .gov, .net, .org. Resolver obtains the IP address from the Top Level Domain (TLD) and also stores it in the cache for later use.
- Browser initiates TCP connection with the server where the website is hosted.
- A connection is built between the client and the server.
  -- Browser sends the HTTP request to the server.
  -- Server processes request and sends back a response.
  -- The browser renders the content that has been requested.
- The browser parses HTML into a DOM tree and includes tokenization (start and end tags, attribute names and values) and tree construction.
  -- In case the HTML parser encounters a non-blocking resources (eg image), it requests those resources and continue parsing.
  -- On encountering CSS styles, it parses the text into the CSS Object Model (or CSSOM), a data structure it then uses for styling layouts and painting. 
  -- The browser then creates a render tree from both these structures to paint the content to the screen. JavaScript is also downloaded, parsed, and then executed.
  -- JavaScript parsing is done during compile time or whenever the parser is invoked, such as during a call to a method.
- Finally, the browser renders the content.

                     --------------                           ---------------
               -->  |Browser Cache |                    --> |  Root Server  |
               |      --------------                    |     ---------------
               |                                        |
 ----------    |    -------------        ----------     |     ---------------
| Browser  |---- > |  OS Cache   |----> | Resolver | ------> |  TLD Server   |
| (Client) |   |   |             |      |  (ISP)   |    |    |               |
 ----------    |    -------------        ----------     |     ---------------
               |                                        |
               |                                        |     ---------------
               |    -------------                       ---> | Authoritative |
               --> | Router Cache|                           | Name Server   |
                    -------------                             ---------------
     