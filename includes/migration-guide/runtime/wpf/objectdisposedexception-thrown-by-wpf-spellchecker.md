### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a>Von der WPF-Rechtschreibprüfung ausgelöste ObjectDisposedException-Ausnahme

|   |   |
|---|---|
|Details|WPF-Anwendungen stürzen beim Beenden der Anwendung gelegentlich ab. Dabei löst die Rechtschreibprüfung die Ausnahme <xref:System.ObjectDisposedException?displayProperty=name> aus. Dies wurde in WPF für .NET 4.7 behoben, indem die Ausnahme ordnungsgemäß verarbeitet wird. Dadurch wird sichergestellt, dass die Anwendungen nicht mehr beeinträchtigt werden. Es ist zu beachten, dass auch weiterhin gelegentlich nicht abgefangene Ausnahmen bei Anwendungen auftreten, die unter einem Debugger ausgeführt werden.|
|Vorschlag|Führen Sie ein Upgrade auf .NET 4.7 durch.|
|Bereich|Microsoft Edge|
|Version|4.6.1|
|Typ|Laufzeit|

