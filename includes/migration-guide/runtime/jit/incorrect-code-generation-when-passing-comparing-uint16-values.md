### <a name="incorrect-code-generation-when-passing-and-comparing-uint16-values"></a>Falsche Codegenerierung bei der Übergabe und dem Vergleich von UInt16-Werten

|   |   |
|---|---|
|Details|Aufgrund von Änderungen, die in .NET Framework 4.7 eingeführt wurden, vergleicht der Code, der vom JIT-Compiler generiert wird, in Anwendungen, die unter .NET Framework 4.7 ausgeführt werden, manchmal zwei <code>T:System.UInt16</code>-Werte fehlerhaft miteinander. Weitere Informationen finden Sie unter [Problem 11508: Silent bad codegen when passing and comparing ushort args](https://github.com/dotnet/coreclr/issues/11508) (Lautlose, ungültige Codegenerierung beim Übergeben und Vergleichen von ushort-Argumenten) auf GitHub.com.|
|Vorschlag|Wenn Sie beim Vergleichen von unsignierten 16-Bit-Werten in .NET Framework 4.7 auf ein Problem stoßen, führen Sie ein Upgrade auf .NET Framework 4.7.1 aus.|
|Bereich|Microsoft Edge|
|Version|4.7|
|Typ|Laufzeit|

