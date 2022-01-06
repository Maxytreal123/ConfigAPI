# ConfigAPI
A Minecraft/Java Based Config API

# Features
- Custom File Extensions Saving

# How To use
- Creating new Config File
```java
public Configuration config, configSaving = ConfigurationAPI.newConfiguration(new File("/test.pix"));
```

- Saving
```java
public void saveConfig() {
    configSaving.set("myKey", false); // The Value can be set anything from string to boolean, int, float, double, long, etc
    
    try {
        configSaving.save();
    } catch (IOException e) {
        e.printTraceStack();
    }
}
```

- Loading
```java
public void loadConfig() {
    try {
        config = ConfigurationAPI.loadExistingConfiguration(new File("/test.pix"));
    } catch (IOException e) {
        e.printTraceStack();
    }
}
```

- Getting From Config
```java
public Config config = new Config();
public boolean value;

// were your client starts
public void init() {
    config.loadConfig();

    value = (boolean) config.config.get("myKey"); // it returns to an object
}
```

- Saving before exit
```java
// were your client stops
public void stop() {
    config.saveConfig(); // Saves Before Minecraft closes
}
```

Big Thanks to: Whomaxiswell#7002
Note: You need an library to add (its in the Repo)

Contact Whomaxiswell#7002 for more information/errors