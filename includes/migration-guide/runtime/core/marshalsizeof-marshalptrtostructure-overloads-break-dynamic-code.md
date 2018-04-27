### <a name="marshalsizeof-and-marshalptrtostructure-overloads-break-dynamic-code"></a>Marshal.SizeOf- und Marshal.PtrToStructure-Überladungen führen bei dynamischem Code zu Fehlern

|   |   |
|---|---|
|Details|Ab .NET Framework 4.5.1 kann das dynamische Binden an die Methoden <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601>, <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601(%60%600)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Object)>,<xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Type)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr)> oder <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr,%60%600)> (z.B. über Windows PowerShell, IronPython oder das C#-Schlüsselwort „dynamic“) zu <code>MethodInvocationExceptions</code> führen, da neue Überladungen dieser Methoden hinzugefügt wurden, die für die Skript-Engines möglicherweise mehrdeutig sind.|
|Vorschlag|Aktualisieren Sie die Skripts, um eindeutig anzugeben, welche Überladung verwendet werden muss. Dies kann in der Regel dadurch erreicht werden, dass die Typparameter der Methoden explizit zu <xref:System.Type> umgewandelt werden. Weitere Informationen und Beispiele zur Problemumgehung finden Sie über [diesen Link](https://support.microsoft.com/kb/2909958/).|
|Bereich|Gering|
|Version|4.5.1|
|Typ|Laufzeit|

