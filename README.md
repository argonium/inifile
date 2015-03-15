# IniFile
IniFile is a Java class that can read and write a Windows-style INI file. INI files are plain text files that usually look similar to this:

```
  [drivers]
  wave=mmdrv.dll
  timer=timer.drv

  [386enh]
  woafont=dosapp.FON
  EGA40WOA.FON=EGA40WOA.FON
```

In this section, "drivers" and "386enh" are sections, and fields such as "wave" and "timer" are properties. An IniFile object is instantiated with this constructor:

```
  IniFile ini = new IniFile(String iniFileName)
```

The class has getters and setters for booleans, integers, longs, doubles, dates and strings. Each getter can be provided with an optional value to return if the section and property are not found. The public methods in the IniFile class are:

```
  public boolean getBooleanProperty(String sectionName,
                                    String propertyName)
  public boolean getBooleanProperty(String sectionName,
                                    String propertyName,
                                    boolean defaultValue)
  public int getIntegerProperty(String sectionName,
                                String propertyName)
  public int getIntegerProperty(String sectionName,
                                String propertyName,
                                int defaultValue)
  public long getLongProperty(String sectionName,
                              String propertyName)
  public long getLongProperty(String sectionName,
                              String propertyName,
                              long defaultValue)
  public double getDoubleProperty(String sectionName,
                                  String propertyName)
  public double getDoubleProperty(String sectionName,
                                  String propertyName,
                                  double defaultValue)
  public Date getDateProperty(String sectionName,
                              String propertyName)
  public String getStringProperty(String sectionName,
                                  String propertyName)
  public String getStringProperty(String sectionName,
                                  String propertyName,
                                  String defaultValue)
  public boolean setBooleanProperty(String sectionName,
                                    String propertyName,
                                    boolean value)
  public boolean setIntegerProperty(String sectionName,
                                    String propertyName,
                                    int value)
  public boolean setLongProperty(String sectionName,
                                 String propertyName,
                                 long value)
  public boolean setDoubleProperty(String sectionName,
                                   String propertyName,
                                   double value)
  public boolean setDateProperty(String sectionName,
                                 String propertyName,
                                 Date value)
  public boolean setStringProperty(String sectionName,
                                   String propertyName,
                                   String value)
  public List getAllPropertyNames(String sectionName)
  public Set getAllSectionNamesAsHashSet()
  public List getAllSectionNames()
  public String getIniFilename()
```

Update 1: Colm Smyth has graciously added some helpful methods:

```
  public Map<String, Map<String, String>> getAllPropertiesInAllSections()
  public Map<String, String> getAllPropertiesInSection(String sectionName)
  public Map<String, String> getAllPropertiesInSection(String sectionName,
                                                       Map<String, String> props)
  public BufferedReader getAllPropertiesInCurrentSection(
                                Map<String, String> props,
                                BufferedReader in,
                                Collection<String> sections)
```

Update 2: Sven Schliesing has graciously added this helpful method:

```
  public Properties getAsProperties()
```

Thanks, Colm and Sven!

Date objects are read and written as long integers (the number of milliseconds since January 1, 1970 UTC).

The source code is released under the MIT license.
