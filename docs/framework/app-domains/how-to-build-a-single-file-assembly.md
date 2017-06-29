---
title: 'Vorgehensweise: Erstellen einer Einzeldateiassembly | Microsoft-Dokumentation'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assembly manifest, single-file assemblies
- library assemblies
- command-line compilers
- assemblies [.NET Framework], single-file
- output file name for assemblies
- code modules
- single-file assemblies
ms.assetid: a6063221-43a5-4d3e-814c-288a4ec69aec
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0ddf25f1d588c0972381a54ee0da4b35e3c0dc33
ms.contentlocale: de-de
ms.lasthandoff: 06/02/2017

---
# <a name="how-to-build-a-single-file-assembly"></a>Gewusst wie: Erstellen einer Einzeldateiassembly
Eine Einzeldateiassembly, die den einfachsten Assemblytyp darstellt, enthält eine Typinformation und Implementierung sowie das [Assemblymanifest](../../../docs/framework/app-domains/assembly-manifest.md). Sie können Befehlszeilencompiler oder [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] verwenden, um eine Einzeldateiassembly zu erstellen. Standardmäßig erstellt der Compiler eine Assemblydatei mit einer „.exe“-Erweiterung.  
  
> [!NOTE]
>  [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] für C# und Visual Basic kann nur genutzt werden, um Einzeldateiassemblys zu erstellen. Wenn Sie Mehrfachdateiassemblys erstellen möchten, müssen Sie Befehlszeilencompiler oder [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] für Visual C++ verwenden.  
  
 Das folgende Verfahren zeigt Ihnen, wie Sie Einzeldateiassemblys mithilfe von Befehlszeilencompiler erstellen.  
  
### <a name="to-create-an-assembly-with-an-exe-extension"></a>So erstellen Sie eine Assembly mit einer „.exe“-Erweiterung  
  
1.  Geben Sie an der Eingabeaufforderung folgenden Befehl ein:  
  
     \<*compilerbefehl*> \<*modulname*>  
  
     In diesem Befehl ist *compilername* der Compilerbefehl für die Sprache, die in Ihrem Codemodul verwendet wird, und *modulname* ist der Name des Codemoduls, um in die Assembly zu kompilieren.  
  
 Das folgende Beispiel erstellt eine Assembly namens `myCode.exe` aus einem Codemodul namens `myCode`.  
  
```csharp  
csc myCode.cs  
```  
  
```vb  
vbc myCode.vb  
```  
  
#### <a name="to-create-an-assembly-with-an-exe-extension-and-specify-the-output-file-name"></a>So erstellen Sie eine Assembly mit einer „.exe“-Erweiterung und geben den Namen der Ausgabedatei an  
  
1.  Geben Sie an der Eingabeaufforderung folgenden Befehl ein:  
  
     \<*compilerbefehl*> **/out:**\<*dateiname*> \<*modulname*>  
  
     In diesem Befehl ist *compilerbefehl* der Compilerbefehl für die in Ihrem Codemodul verwendete Sprache, *dateiname* ist der Name der Ausgabedatei und *modulname* der Name des Codemodul, das in die Assembly kompiliert wird.  
  
 Das folgende Beispiel erstellt eine Assembly namens `myAssembly.exe` aus einem Codemodul namens `myCode`.  
  
```csharp  
csc /out:myAssembly.exe myCode.cs  
```  
  
```vb  
vbc /out:myAssembly.exe myCode.vb  
```  
  
## <a name="creating-library-assemblies"></a>Erstellen von Bibliothekassemblys  
 Eine Bibliotheksassembly ist ähnlich wie eine Klassenbibliothek. Sie enthält Typen, die von anderen Assemblys verwiesen werden, jedoch besitzt sie keinen Einstiegspunkt zum Starten der Ausführung.  
  
#### <a name="to-create-a-library-assembly"></a>So erstellen Sie eine Bibliotheksassembly  
  
1.  Geben Sie an der Eingabeaufforderung folgenden Befehl ein:  
  
     \<*compilerbefehl*> **/t:library** \<*modulname*>  
  
     In diesem Befehl ist *compilername* der Compilerbefehl für die Sprache, die in Ihrem Codemodul verwendet wird, und *modulname* ist der Name des Codemoduls, um in die Assembly zu kompilieren. Sie können auch andere Compileroptionen verwenden, z.B. die Option **/out:**.  
  
 Das folgende Beispiel erstellt eine Bibliotheksassembly namens `myCodeAssembly.dll` aus einem Codemodul namens `myCode`.  
  
```csharp  
csc /out:myCodeLibrary.dll /t:library myCode.cs  
```  
  
```vb  
vbc /out:myCodeLibrary.dll /t:library myCode.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Assemblys](../../../docs/framework/app-domains/create-assemblies.md)   
 [Mehrfachdateiassemblys](../../../docs/framework/app-domains/multifile-assemblies.md)   
 [Vorgehensweise: Erstellen einer Mehrfachdateiassembly](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)   
 [Programmieren mit Assemblys](../../../docs/framework/app-domains/programming-with-assemblies.md)
