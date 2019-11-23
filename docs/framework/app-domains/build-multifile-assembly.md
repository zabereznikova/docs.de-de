---
title: 'How to: Build a multifile assembly'
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- entry point for assembly
- compiling assemblies
- Al.exe
- command-line compilers
- assembly manifest, multifile assemblies
- assemblies [.NET Framework], compiling
- Assembly Linker
- code modules
- multifile assemblies
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 261c5583-8a76-412d-bda7-9b8ee3b131e5
ms.openlocfilehash: 0f8c6d57425657e321d80f9edffa20f27bc28770
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429565"
---
# <a name="how-to-build-a-multifile-assembly"></a>How to: Build a multifile assembly

In diesem Artikel wird beschrieben, wie eine Mehrfachdateiassembly erstellt wird, und es wird Code vorgestellt, der jeden Schritt in der Vorgehensweise veranschaulicht.

> [!NOTE]
> Die Visual Studio-IDE für C# und Visual Basic kann nur zum Erstellen von Einzeldateiassemblys verwendet werden. Wenn Sie Mehrfachdateiassemblys erstellen möchten, müssen Sie auf Befehlszeilencompiler oder auf Visual Studio mit Visual C++ zurückgreifen. Mehrfachdateiassemblys werden nur im .NET Framework unterstützt.

## <a name="create-a-multifile-assembly"></a>Erstellen einer Mehrfachdateiassembly

1. Kompilieren Sie alle Dateien mit Namespaces, auf die andere Module der Assembly verweisen, in Codemodule. Die Standarderweiterung für Codemodule ist *.netmodule*.

   Beispielsweise weist die Datei `Stringer` den Namespace `myStringer` auf, der die Klasse `Stringer` enthält. Die `Stringer`-Klasse enthält die `StringerMethod`-Methode, die eine einzelne Zeile auf der Konsole ausgibt.

   ```cpp
   // Assembly building example in the .NET Framework.
   using namespace System;

   namespace myStringer
   {
       public ref class Stringer
       {
       public:
           void StringerMethod()
           {
               System::Console::WriteLine("This is a line from StringerMethod.");
           }
       };
   }
   ```

   ```csharp
   // Assembly building example in the .NET Framework.
   using System;

   namespace myStringer
   {
       public class Stringer
       {
           public void StringerMethod()
           {
               System.Console.WriteLine("This is a line from StringerMethod.");
           }
       }
   }
   ```

   ```vb
   ' Assembly building example in the .NET Framework.
   Namespace myStringer
       Public Class Stringer
           Public Sub StringerMethod()
               System.Console.WriteLine("This is a line from StringerMethod.")
           End Sub
       End Class
   End Namespace
   ```

2. Verwenden Sie folgenden Befehl, um diesen Code zu kompilieren:

   ```cpp
   cl /clr:pure /LN Stringer.cpp
   ```

   ```csharp
   csc /t:module Stringer.cs
   ```

   ```vb
   vbc /t:module Stringer.vb
   ```

   Durch die Compileroption **/t:** in Verbindung mit dem Parameter *module* wird die Datei als Modul kompiliert, nicht als Assembly. Der Compiler erzeugt ein Modul mit dem Namen *Stringer.netmodule*, das anschließend einer Assembly hinzugefügt werden kann.

3. Kompilieren Sie alle weiteren Module unter Verwendung der erforderlichen Compileroptionen, um die anderen Module anzugeben, auf die im Code verwiesen wird. In diesem Schritt kommt die **/addmodule**-Compileroption zum Einsatz.

   Im folgenden Beispiel verfügt ein Codemodul mit dem Namen *Client* über die `Main`-Methode als Einstiegspunkt. Diese verweist wiederum auf eine Methode im *Stringer.dll*-Modul, das in Schritt 1 erstellt wurde.

   ```cpp
   #using "Stringer.netmodule"

   using namespace System;
   using namespace myStringer; //The namespace created in Stringer.netmodule.

   ref class MainClientApp
   {
       // Static method Main is the entry point method.
   public:
       static void Main()
       {
           Stringer^ myStringInstance = gcnew Stringer();
           Console::WriteLine("Client code executes");
           myStringInstance->StringerMethod();
       }
   };

   int main()
   {
       MainClientApp::Main();
   }
   ```

   ```csharp
   using System;
   using myStringer;

   class MainClientApp
   {
       // Static method Main is the entry point method.
       public static void Main()
       {
           Stringer myStringInstance = new Stringer();
           Console.WriteLine("Client code executes");
           myStringInstance.StringerMethod();
       }
   }
   ```

   ```vb
   Imports myStringer

   Class MainClientApp
       ' Static method Main is the entry point method.
       Public Shared Sub Main()
           Dim myStringInstance As New Stringer()
           Console.WriteLine("Client code executes")
           myStringInstance.StringerMethod()
       End Sub
   End Class
   ```

4. Verwenden Sie folgenden Befehl, um diesen Code zu kompilieren:

   ```cpp
   cl /clr:pure /FUStringer.netmodule /LN Client.cpp
   ```

   ```csharp
   csc /addmodule:Stringer.netmodule /t:module Client.cs
   ```

   ```vb
   vbc /addmodule:Stringer.netmodule /t:module Client.vb
   ```

   Verwenden Sie die Option **/t:module**, da dieses Modul in einem späteren Schritt zu einer Assembly hinzugefügt wird. Legen Sie die Option **/addmodule** fest, da der Code in *Client* auf einen Namespace verweist, der vom Code in *Stringer.netmodule* erzeugt wurde. Der Compiler erzeugt ein Modul mit dem Namen *Client.netmodule*, das einen Verweis auf ein anderes Modul namens *Stringer.netmodule* enthält.

   > [!NOTE]
   > Die C#- und Visual Basic-Compiler unterstützen das direkte Erstellen von Mehrfachdateiassemblys unter Verwendung der beiden folgenden unterschiedlichen Syntaxformen.
   >
   > Zwei Kompilierungen erzeugen eine aus zwei Dateien bestehende Assembly:
   >
   >   ```cpp
   >   cl /clr:pure /LN Stringer.cpp
   >   cl /clr:pure Client.cpp /link /ASSEMBLYMODULE:Stringer.netmodule
   >   ```
   >
   >   ```csharp
   >   csc /t:module Stringer.cs
   >   csc Client.cs /addmodule:Stringer.netmodule
   >   ```
   >
   >   ```vb
   >   vbc /t:module Stringer.vb
   >   vbc Client.vb /addmodule:Stringer.netmodule
   >   ```
   >
   > Eine Kompilierung erzeugt eine aus zwei Dateien bestehende Assembly:
   >
   >   ```cpp
   >   cl /clr:pure /LN Stringer.cpp
   >   cl /clr:pure Client.cpp /link /ASSEMBLYMODULE:Stringer.netmodule
   >   ```
   >
   >   ```csharp
   >   csc /out:Client.exe Client.cs /out:Stringer.netmodule Stringer.cs
   >   ```
   >
   >   ```vb
   >   vbc /out:Client.exe Client.vb /out:Stringer.netmodule Stringer.vb
   >   ```

5. Erstellen Sie mit dem [Assembly Linker-Tool (Al.exe)](../tools/al-exe-assembly-linker.md) eine Ausgabedatei, die das Assemblymanifest enthält. In dieser Datei sind Referenzinformationen zu allen zur Assembly gehörenden Modulen und Ressourcen enthalten.

    Geben Sie an der Eingabeaufforderung folgenden Befehl ein:

    **al** \<*modulname*> \<*modulname*> … **/main:** \<*Methodenname*>  **/out:** \<*Dateiname*>  **/target:** \<*Assemblydateityp*>

    In diesem Befehl bezeichnen die *Modulname*-Argumente die Namen aller Module, die in der Assembly enthalten sein sollen. Die Option **/main:** gibt den Methodennamen an, der den Einstiegspunkt der Assembly darstellt. Die Option **/out:** gibt den Namen der Ausgabedatei an, die Assemblymetadaten enthält. Die Option **/target:** gibt an, dass die Assembly eine ausführbare Datei für eine Konsolenanwendung ( *.exe*), eine ausführbare Windows-Datei ( *.win*) oder eine Bibliothek ist ( *.lib*).

    Im folgenden Beispiel erstellt *Al.exe* eine Assembly mit dem Namen *myAssembly.exe*, die eine ausführbare Datei für eine Konsolenanwendung ist. Die Anwendung besteht aus den zwei Modulen *Client.netmodule* und *Stringer.netmodule* sowie der ausführbaren Datei *myAssembly.exe*, die ausschließlich Assemblymetadaten enthält. Der Einstiegspunkt der Assembly ist die `Main`-Methode in der `MainClientApp`-Klasse, die sich in der *Client.dll* befindet.

    ```cmd
    al Client.netmodule Stringer.netmodule /main:MainClientApp.Main /out:myAssembly.exe /target:exe
    ```

    Sie können das [MSIL Disassembler-Tool (Ildasm.exe)](../tools/ildasm-exe-il-disassembler.md) verwenden, um den Inhalt einer Assembly zu untersuchen oder um zu bestimmen, ob es sich bei einer Datei um eine Assembly oder ein Modul handelt.

## <a name="see-also"></a>Siehe auch

- [Erstellen von Assemblys](../../standard/assembly/create.md)
- [How to: View assembly contents](../../standard/assembly/view-contents.md)
- [So sucht Common Language Runtime nach Assemblys](../deployment/how-the-runtime-locates-assemblies.md)
- [Mehrfachdateiassemblys](multifile-assemblies.md)
