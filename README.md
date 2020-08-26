# RedisEndpoint
## Prerequisite
1. A running [Redis(Ubuntu/WSL)](https://redis.io/)/[Memurai(Windows)](https://www.memurai.com/) server
## Usage
### Example
```csharp
Using RedisEndpoint;

namespace Example
{
    class Program
    {
        const string URL = "localhost";
        const ushort PORT = 6380;
        private static Subscriber mySubscriber = new Subscriber(URL, PORT);

        static int Main()
        {
            mySubscriber.SubscribeTo("TARGET_CHANNEL");
            mySubscriber.msgQueue.OnMessage(msg => {
                //msg.Channel = Channel Name
                //msg.Message = Input Message
            });
            _ = Console.ReadKey();
            return 0;
        }
    }
}
```