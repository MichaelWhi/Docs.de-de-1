Die folgende Tabelle zeigt die Details der Parameter des Codegenerators von ASP.NET:

| Parameter               | Beschreibung|
| ----------------- | ------------ |
| -m  | Der Name des Modells. |
| -dc  | Die `DbContext`-Klasse, die verwendet werden soll. |
| -udl | Verwendung des Standardlayouts. |
| -outDir | Der relative Ausgabeordnerpfad zur Erstellung der Ansichten. |
| --referenceScriptLibraries | Fügt `_ValidationScriptsPartial` zu den Seiten „Create“ und „Edit“ hinzu. |

Verwenden Sie den `h`-Switch um Hilfe für den `aspnet-codegenerator razorpage`-Befehl zu erhalten:

```console
dotnet aspnet-codegenerator razorpage -h
```
