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
        const ushort PORT = 6379;
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
### Implemented Event Detectors
1. HIT ( BF1, HLA(WIP) )
2. FIRE (BF1, HLA(WIP) )
3. ACCELX (PC2)
4. ACCELY (PC2)