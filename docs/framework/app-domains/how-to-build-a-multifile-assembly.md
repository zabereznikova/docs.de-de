---
title: 'Gewusst wie: Erstellen einer Mehrfachdateiassembly'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
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
ms.assetid: 261c5583-8a76-412d-bda7-9b8ee3b131e5
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f77922d08ce17f8b8659eac0dba5a46ca33a7502
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-build-a-multifile-assembly"></a>Gewusst wie: Erstellen einer Mehrfachdateiassembly
In diesem Artikel wird beschrieben, wie eine Mehrfachdateiassembly erstellt wird, und es wird Code vorgestellt, der jeden Schritt in der Vorgehensweise veranschaulicht.  
  
> [!NOTE]
>  Die Visual Studio-IDE für C# und Visual Basic kann nur zum Erstellen von Einzeldateiassemblys verwendet werden. Wenn Sie Mehrfachdateiassemblys erstellen möchten, müssen Sie auf Befehlszeilencompiler oder auf Visual Studio mit Visual C++ zurückgreifen.  
  
### <a name="to-create-a-multifile-assembly"></a>So erstellen Sie eine Mehrfachdateiassembly  
  
1.  Kompilieren Sie alle Dateien mit Namespaces, auf die andere Module der Assembly verweisen, in Codemodule. Die Standarderweiterung für Codemodule ist "netmodule".  
  
     Beispielsweise weist die Datei `Stringer` den Namespace `myStringer` auf, der die Klasse `Stringer` enthält. Die `Stringer`-Klasse enthält die `StringerMethod`-Methode, die eine einzelne Zeile auf der Konsole ausgibt.  
  
     [!code-cpp[Conceptual.Assembly.Multifile#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/stringer.cpp#1)]
     [!code-csharp[Conceptual.Assembly.Multifile#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/stringer.cs#1)]
     [!code-vb[Conceptual.Assembly.Multifile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/stringer.vb#1)]  
  
     Verwenden Sie folgenden Befehl, um diesen Code zu kompilieren:  
  
     [!code-cpp[Conceptual.Assembly.Multifile#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/stringer.cpp#2)]
     [!code-csharp[Conceptual.Assembly.Multifile#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/stringer.cs#2)]
     [!code-vb[Conceptual.Assembly.Multifile#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/stringer.vb#2)]  
  
     Durch die Compileroption **/t:** in Verbindung mit dem Parameter *module* wird die Datei als Modul kompiliert, nicht als Assembly. Der Compiler erzeugt ein Modul mit dem Namen `Stringer.netmodule`, das anschließend einer Assembly hinzugefügt werden kann.  
  
2.  Kompilieren Sie alle weiteren Module unter Verwendung der erforderlichen Compileroptionen, um die anderen Module anzugeben, auf die im Code verwiesen wird. In diesem Schritt kommt die **/addmodule**-Compileroption zum Einsatz.  
  
     Im folgenden Beispiel verfügt ein Codemodul mit dem Namen `Client` über die `Main`-Methode als Einstiegspunkt. Diese verweist wiederum auf eine Methode im `Stringer.dll`-Modul, das in Schritt 1 erstellt wurde.  
  
     [!code-cpp[Conceptual.Assembly.Multifile#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#3)]
     [!code-csharp[Conceptual.Assembly.Multifile#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#3)]
     [!code-vb[Conceptual.Assembly.Multifile#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#3)]  
  
     Verwenden Sie folgenden Befehl, um diesen Code zu kompilieren:  
  
     [!code-cpp[Conceptual.Assembly.Multifile#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#4)]
     [!code-csharp[Conceptual.Assembly.Multifile#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#4)]
     [!code-vb[Conceptual.Assembly.Multifile#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#4)]  
  
     Verwenden Sie die Option **/t:module**, da dieses Modul in einem späteren Schritt zu einer Assembly hinzugefügt wird. Legen Sie die **/addmodule**-Option fest, da der Code in `Client` auf einen Namespace verweist, der vom Code in `Stringer.netmodule` erzeugt wurde. Der Compiler erzeugt ein Modul mit dem Namen `Client.netmodule`, das einen Verweis auf ein anderes Modul, `Stringer.netmodule`, enthält.  
  
    > [!NOTE]
    >  Die C#- und Visual Basic-Compiler unterstützen das direkte Erstellen von Mehrfachdateiassemblys unter Verwendung der beiden folgenden unterschiedlichen Syntaxformen.  
    >   
    >  -   Zwei Kompilierungen erzeugen eine aus zwei Dateien bestehende Assembly:  
    >   
    >      [!code-cpp[Conceptual.Assembly.Multifile#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#5)]
      [!code-csharp[Conceptual.Assembly.Multifile#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#5)]
      [!code-vb[Conceptual.Assembly.Multifile#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#5)]  
    > -   Eine Kompilierung erzeugt eine aus zwei Dateien bestehende Assembly:  
    >   
    >      [!code-cpp[Conceptual.Assembly.Multifile#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#6)]
      [!code-csharp[Conceptual.Assembly.Multifile#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#6)]
      [!code-vb[Conceptual.Assembly.Multifile#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#6)]  
  
3.  Erstellen Sie mit dem [Assembly Linker-Tool (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) eine Ausgabedatei, die das Assemblymanifest enthält. In dieser Datei sind Referenzinformationen zu allen zur Assembly gehörenden Modulen und Ressourcen enthalten.  
  
     Geben Sie an der Eingabeaufforderung folgenden Befehl ein:  
  
     **al** \<*modulname*> \<*modulname*> … **/main:**\<*Methodenname*> **/out:**\<*Dateiname*> **/target:**\<*Assemblydateityp*>  
  
     In diesem Befehl bezeichnen die *Modulname*-Argumente die Namen aller Module, die in der Assembly enthalten sein sollen. Die Option **/main:** gibt den Methodennamen an, der den Einstiegspunkt der Assembly darstellt. Die Option **/out:** gibt den Namen der Ausgabedatei an, die Assemblymetadaten enthält. Die Option **/target:** gibt an, dass die Assembly eine ausführbare Datei für eine Konsolenanwendung (.exe), eine ausführbare Windows-Datei (.win) oder eine Bibliothek ist (.lib).  
  
     Im folgenden Beispiel erstellt Al.exe`myAssembly.exe` eine Assembly mit dem Namen , die eine ausführbare Datei für eine Konsolenanwendung ist. Die Anwendung besteht aus zwei Modulen, `Client.netmodule` und `Stringer.netmodule`, sowie der ausführbaren Datei `myAssembly.exe,`, die ausschließlich Assemblymetadaten enthält. Der Einstiegspunkt der Assembly ist die `Main`-Methode in der `MainClientApp`-Klasse, die sich in der Datei `Client.dll` befindet.  
  
    ```  
    al Client.netmodule Stringer.netmodule /main:MainClientApp.Main /out:myAssembly.exe /target:exe   
    ```  
  
     Sie können das [MSIL Disassembler-Tool (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) verwenden, um den Inhalt einer Assembly zu untersuchen oder um zu bestimmen, ob es sich bei einer Datei um eine Assembly oder ein Modul handelt.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Assemblys](../../../docs/framework/app-domains/create-assemblies.md)  
 [Gewusst wie: Anzeigen des Assemblyinhalts](../../../docs/framework/app-domains/how-to-view-assembly-contents.md)  
 [So sucht Common Language Runtime nach Assemblys](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [Mehrfachdateiassemblys](../../../docs/framework/app-domains/multifile-assemblies.md)
