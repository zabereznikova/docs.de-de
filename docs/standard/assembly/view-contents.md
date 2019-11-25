---
title: 'Vorgehensweise: Anzeigen des Assemblyinhalts'
ms.date: 08/20/2019
helpviewer_keywords:
- assembly manifest, viewing information
- Ildasm.exe
- MSIL Disassembler
- assemblies [.NET Framework], viewing contents
- viewing assembly information
- MSIL
- viewing MSIL information
ms.assetid: fb7baaab-4c0d-47ad-8fd3-4591cf834709
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 72b02209d74b6b183af6c11d9bd037889ea08543
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347060"
---
# <a name="how-to-view-assembly-contents"></a>Vorgehensweise: Anzeigen des Assemblyinhalts

Sie können den [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) verwenden, um Microsoft Intermediate Language-Informationen (MSIL) in einer Datei anzuzeigen. Wenn die untersuchte Datei eine Assembly ist, kann die Information die Attribute der Assembly enthalten sowie Verweise auf andere Module und Assemblys. Diese Informationen sind nützlich, um zu ermitteln, ob eine Datei eine Assembly oder Teil einer Assembly ist und ob die Datei über Verweise auf andere Module oder Assemblys verfügt.

Wenn Sie den Inhalt einer Assembly mithilfe von *Ildasm.exe* anzeigen möchten, geben Sie in einer Eingabeaufforderung **ildasm\<Assemblyname>** ein. Beispielsweise disassembliert der folgende Befehl die *Hello.exe*-Assembly.

```cmd
ildasm Hello.exe
```

Klicken Sie doppelt auf das **Manifest**-Symbol im Fenster „MSIL-Disassembler“, um Informationen zum Assemblymanifest anzuzeigen.

## <a name="example"></a>Beispiel

Das folgende Beispiel beginnt mit einem einfachen „Hallo Welt“-Programm. Nachdem Sie das Programm kompiliert haben, verwenden Sie *Ildasm.exe*, um das *Hello.exe*-Assembly zu disassemblieren, und zeigen Sie das Assemblymanifest an.

```cpp
using namespace System;

class MainApp
{
public:
    static void Main()
    {
        Console::WriteLine("Hello World using C++/CLI!");
    }
};

int main()
{
    MainApp::Main();
}
```

```csharp
using System;

class MainApp
{
    public static void Main()
    {
        Console.WriteLine("Hello World using C#!");
    }
}
```

```vb
Class MainApp
    Public Shared Sub Main()
        Console.WriteLine("Hello World using Visual Basic!")
    End Sub
End Class
```

Führen Sie den Befehl *ildasm.exe* noch mal in der *Hello.exe*-Assembly aus, und führen Sie eine Doppelklick auf das **Manifest**-Symbol im Fenster „MSIL Disassembler“ durch, wodurch folgende Ausgabe erzeugt wird:

```output
// Metadata version: v4.0.30319
.assembly extern mscorlib
{
  .publickeytoken = (B7 7A 5C 56 19 34 E0 89 )                         // .z\V.4..
  .ver 4:0:0:0
}
.assembly Hello
{
  .custom instance void [mscorlib]System.Runtime.CompilerServices.CompilationRelaxationsAttribute::.ctor(int32) = ( 01 00 08 00 00 00 00 00 )
  .custom instance void [mscorlib]System.Runtime.CompilerServices.RuntimeCompatibilityAttribute::.ctor() = ( 01 00 01 00 54 02 16 57 72 61 70 4E 6F 6E 45 78   // ....T..WrapNonEx
                                                                                                             63 65 70 74 69 6F 6E 54 68 72 6F 77 73 01 )       // ceptionThrows.
  .hash algorithm 0x00008004
  .ver 0:0:0:0
}
.module Hello.exe
// MVID: {7C2770DB-1594-438D-BAE5-98764C39CCCA}
.imagebase 0x00400000
.file alignment 0x00000200
.stackreserve 0x00100000
.subsystem 0x0003       // WINDOWS_CUI
.corflags 0x00000001    //  ILONLY
// Image base: 0x00600000
```

In der folgenden Tabelle wird jede Anweisung im Assemblymanifest der Assembly *Hello.exe* beschrieben, die im Beispiel verwendet wird:

|Anweisung|BESCHREIBUNG|
|---------------|-----------------|
|**.assembly extern \<assemblyname>**|Gibt eine andere Assembly an, die Elemente enthält, auf die vom aktuellen Modul verwiesen wird (in diesem Beispiel `mscorlib`).|
|**.publickeytoken \<token>**|Gibt den Token des tatsächlichen Schlüssels der verwiesenen Assembly an.|
|**.ver \<versionsnummer>**|Gibt die Versionsnummer der verwiesenen Assembly an.|
|**.assembly \<assemblyname>**|Gibt den Assemblynamen an.|
|**.hash algorithm \<int32-wert>**|Gibt den verwendeten Hashalgorithmus an.|
|**.ver \<versionsnummer>**|Gibt die Versionsnummer der Assembly an.|
|**.module \<dateiname>**|Gibt den Namen der Module an, aus die eine Assembly besteht. In diesem Beispiel besteht die Assembly aus nur einer Datei.|
|**.subsystem \<wert>**|Gibt die Anwendungsumgebung an, die für das Programm erforderlich ist. In diesem Beispiel gibt der Wert 3 an, dass diese ausführbare Datei von einer Konsole aus ausgeführt wird.|
|**.corflags**|Derzeit ein reserviertes Feld in den Metadaten.|

Ein Assemblymanifest kann eine Reihe unterschiedlicher Direktiven enthalten, je nach den Inhalten der Assembly. Eine ausführliche Liste mit den Anweisungen im Assemblymanifest finden Sie in der ECMA-Dokumentation, insbesondere unter „Partition II: Metadatendefinition und Semantik) und „Partition III: CIL Instruction Set“ (CIL-Anweisungen):

- [Standards von ECMA C# und der Common Language Infrastructure](/dotnet/standard/components#applicable-standards)
- [ECMA-335-Standard: Common Language Infrastructure-Standard (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm)

## <a name="see-also"></a>Siehe auch

- [Anwendungsdomänen und Assemblys](../../framework/app-domains/application-domains.md#application-domains-and-assemblies)
- [Artikel zur Vorgehensweise zu Anwendungsdomänen und Assemblys](../../framework/app-domains/application-domains-and-assemblies-how-to-topics.md)
- [Ildasm.exe (IL-Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md)
