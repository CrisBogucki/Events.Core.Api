# Events Core Api with CQRS 
Segregation with events, comands and queries

![](http://www.ouarzy.com/wp-content/uploads/2016/09/cqsr_pattern.png)

## Using Command
Add commandbus in constructor use dependency inject
```
private readonly ICommandBus commandBus;

public MyController(ICommandBus commandBus)
{
    this.commandBus = commandBus;
}
```

Method 
using by async
```      
public async Task RunCommandAsync()
{
    MessageCommand _msg = new MessageCommand() { ... };
    this.commandBus.SendCommandAsync(_msg);
}
```
or void synchro
```
public void RunCommand()
{
    MessageCommand _msg = new MessageCommand() { ... };
    this.commandBus.SendCommand(_msg);
}
```
