---
title: 'Vorgehensweise: Ermitteln des vollqualifizierten Namens einer Assembly'
description: In diesem Artikel erfahren Sie, wie Sie den vollqualifizierten Namen einer .NET-Assembly abrufen.
ms.date: 08/20/2019
helpviewer_keywords:
- names [.NET], fully qualified type names
- names [.NET], assemblies
- assemblies [.NET], names
ms.assetid: 009dae23-e1f6-4a64-9a9a-32e4c34802b0
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 223def7d992f5fae64c95aa6886f20980184eddc
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687620"
---
# <a name="how-to-find-an-assemblys-fully-qualified-name"></a>Vorgehensweise: Ermitteln des vollqualifizierten Namens einer Assembly

Verwenden Sie das Tool für den globalen Assemblycache ([Gacutil.exe](../../framework/tools/gacutil-exe-gac-tool.md)), um den vollqualifizierten Namen einer .NET Framework-Assembly im globalen Assemblycache zu ermitteln. Weitere Informationen finden Sie unter [How to: Vorgehensweise: Anzeigen der Inhalte des globalen Assemblycaches](../../framework/app-domains/how-to-view-the-contents-of-the-gac.md).

Für .NET Core- und .NET Framework-Assemblys, die sich nicht im globalen Assemblycache befinden, können Sie den vollqualifizierten Assemblynamen auf verschiedene Weisen abrufen:

- Sie können Code verwenden, um die Informationen in der Konsole oder in einer Variable auszugeben, oder Sie können die [Ildasm.exe (IL-Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) verwenden, um die Assemblymetadaten zu überprüfen, die den vollqualifizierten Namen enthalten.

- Wenn die Assembly bereits von der Anwendung geladen wird, können Sie den Wert der <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType>-Eigenschaft abrufen, um den vollqualifizierten Namen abzurufen. Sie können die <xref:System.Type.Assembly>-Eigenschaft einer in dieser Assembly definierten <xref:System.Type>-Klasse verwenden, um einen Verweis auf das <xref:System.Reflection.Assembly>-Objekt abzurufen. Dies wird im Beispiel veranschaulicht.

- Wenn Sie den Dateisystempfad der Assembly kennen, können Sie die <xref:System.Reflection.AssemblyName.GetAssemblyName%2A?displayProperty=nameWithType>-Methoden `static` (C#) oder `Shared` (Visual Basic) aufrufen, um den vollqualifizierten Assemblynamen abzurufen. Im Folgenden finden Sie ein einfaches Beispiel.

  ```csharp
  using System;
  using System.Reflection;

  public class Example
  {
     public static void Main()
     {
        Console.WriteLine(AssemblyName.GetAssemblyName(@".\UtilityLibrary.dll"));
     }
  }
  // The example displays output like the following:
  //   UtilityLibrary, Version=1.1.0.0, Culture=neutral, PublicKeyToken=null
  ```

  ```vb
  Imports System.Reflection

  Public Module Example
     Public Sub Main
        Console.WriteLine(AssemblyName.GetAssemblyName(".\UtilityLibrary.dll"))
     End Sub
  End Module
  ' The example displays output like the following:
  '   UtilityLibrary, Version=1.1.0.0, Culture=neutral, PublicKeyToken=null
  ```

- Sie können den [Ildasm.exe (IL-Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) verwenden, um die Metadaten der Assembly zu überprüfen, die den vollqualifizierten Namen enthalten.

Weitere Informationen zum Festlegen von Assemblyattributen, z. B. Version, Kultur und Assemblyname, finden Sie unter [Festlegen von Assemblyattributen](set-attributes.md). Weitere Informationen zum Vergeben eines starken Namens für eine Assembly finden Sie unter [Erstellen und Verwenden von Assemblys mit starken Namen](create-use-strong-named.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie Sie den vollqualifizierten Namen einer Assembly, die eine angegebene Klasse enthält, in der Konsole anzeigen können. Im Beispiel wird die <xref:System.Type.Assembly?displayProperty=nameWithType>-Eigenschaft verwendet, um einen Verweis auf eine Assembly mit einem Typ abzurufen, der in der Assembly definiert ist.

```cpp
#using <System.dll>
#using <System.Data.dll>

using namespace System;
using namespace System::Reflection;

ref class asmname
{
public:
    static void Main()
    {
        Type^ t = System::Data::DataSet::typeid;
        String^ s = t->Assembly->FullName->ToString();
        Console::WriteLine("The fully qualified assembly name " +
            "containing the specified class is {0}.", s);
    }
};

int main()
{
    asmname::Main();
}
```

```csharp
using System;
using System.Reflection;

class asmname
{
    public static void Main()
    {
        Type t = typeof(System.Data.DataSet);
        string s = t.Assembly.FullName.ToString();
        Console.WriteLine("The fully qualified assembly name " +
            "containing the specified class is {0}.", s);
    }
}
```

```vb
Imports System.Reflection

Class asmname
    Public Shared Sub Main()
        Dim t As Type = GetType(System.Data.DataSet)
        Dim s As String = t.Assembly.FullName.ToString()
        Console.WriteLine("The fully qualified assembly name " +
            "containing the specified class is {0}.", s)
    End Sub
End Class
```

## <a name="see-also"></a>Siehe auch

- [Assemblynamen](names.md)
- [Erstellen von Assemblys](create.md)
- [Erstellen und Verwenden von Assemblys mit starkem Namen](create-use-strong-named.md)
- [Globaler Assemblycache](../../framework/app-domains/gac.md)
- [So sucht Common Language Runtime nach Assemblys](../../framework/deployment/how-the-runtime-locates-assemblies.md)
