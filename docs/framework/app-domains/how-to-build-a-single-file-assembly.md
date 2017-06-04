---
title: "Gewusst wie: Erstellen einer Einzeldateiassembly | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Assemblys [.NET Framework], Einzeldatei"
  - "Assemblymanifest, Einzeldateiassemblys"
  - "Codemodule"
  - "Befehlszeilencompiler"
  - "Bibliothekassemblys"
  - "Ausgabedateiname für Assemblys"
  - "Einzeldateiassemblys"
ms.assetid: a6063221-43a5-4d3e-814c-288a4ec69aec
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Erstellen einer Einzeldateiassembly
Der einfachste Assemblytyp ist die Einfachdateiassembly. Sie enthält Typinformationen und \-implementierung sowie das [Assemblymanifest](../../../docs/framework/app-domains/assembly-manifest.md).  Zum Erstellen einer Einfachdateiassembly können Sie Befehlszeilencompiler oder [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] verwenden.  Der Compiler erstellt standardmäßig eine Assemblydatei mit der Erweiterung **.exe**.  
  
> [!NOTE]
>  [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] für C\# und Visual Basic kann nur verwendet werden, um Einzeldateiassemblys zu erstellen.  Wenn Sie Mehrfachdateiassemblys erstellen möchten, müssen Sie auf Befehlszeilencompiler oder auf [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] für Visual C\+\+ zurückgreifen.  
  
 Im Folgenden wird dargestellt, wie Sie Einfachdateiassemblys mithilfe von Befehlszeilencompilern erstellen können.  
  
### So erstellen Sie eine Assembly mit einer EXE\-Erweiterung  
  
1.  Geben Sie an der Eingabeaufforderung folgenden Befehl ein:  
  
     \<*Compilerkommandomodul*\> \<*name*\>  
  
     In diesem Befehl bezeichnet *Compilerbefehl* den Compilerbefehl für die in Ihrem Codemodul verwendete Sprache und *Modulname* den Namen des Codemoduls, das in die Assembly kompiliert werden soll.  
  
 Durch den folgenden Beispielcode wird aus einem Codemodul mit dem Namen `myCode` eine Assembly mit dem Namen `myCode.exe` erstellt.  
  
```csharp  
csc myCode.cs  
```  
  
```vb  
vbc myCode.vb  
```  
  
#### So erstellen Sie eine Assembly mit der Erweiterung .exe und geben den Ausgabedateinamen an  
  
1.  Geben Sie an der Eingabeaufforderung folgenden Befehl ein:  
  
     \<*Compilerbefehls*\>**\/out:**\<*Dateinamen*\> \<*modulname*\>  
  
     In diesem Befehl bezeichnet *Compilerbefehl* den Compilerbefehl für die in Ihrem Codemodul verwendete Sprache, *Dateiname* den Namen der Ausgabedatei und *Modulname* den Namen des Codemoduls, das in die Assembly kompiliert werden soll.  
  
 Durch den folgenden Beispielcode wird aus einem Codemodul mit dem Namen `myCode` eine Assembly mit dem Namen `myAssembly.exe` erstellt.  
  
```csharp  
csc /out:myAssembly.exe myCode.cs  
```  
  
```vb  
vbc /out:myAssembly.exe myCode.vb  
```  
  
## Erstellen von Bibliothekassemblys  
 Eine Bibliothekassembly ist ähnlich aufgebaut wie eine Klassenbibliothek.  Sie enthält Typen, auf die andere Assemblys verweisen, besitzt aber keinen Einstiegspunkt, um eine Ausführung zu starten.  
  
#### So erstellen Sie eine Bibliothekassembly  
  
1.  Geben Sie an der Eingabeaufforderung folgenden Befehl ein:  
  
     \<*Compilerbefehls*\>**\/t:library** \<*Modulname*\>  
  
     In diesem Befehl bezeichnet *Compilerbefehl* den Compilerbefehl für die in Ihrem Codemodul verwendete Sprache und *Modulname* den Namen des Codemoduls, das in die Assembly kompiliert werden soll.  Sie können auch andere Compileroptionen verwenden, z. B. die Option **\/out:**.  
  
 Durch den folgenden Beispielcode wird aus einem Codemodul mit dem Namen `myCode` eine Bibliothekassembly mit dem Namen `myCodeAssembly.dll` erstellt.  
  
```csharp  
csc /out:myCodeLibrary.dll /t:library myCode.cs  
```  
  
```vb  
vbc /out:myCodeLibrary.dll /t:library myCode.vb  
```  
  
## Siehe auch  
 [Erstellen von Assemblys](../../../docs/framework/app-domains/create-assemblies.md)   
 [Mehrfachdateiassemblys](../../../docs/framework/app-domains/multifile-assemblies.md)   
 [Gewusst wie: Erstellen einer Mehrfachdateiassembly](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)   
 [Programmieren mit Assemblys](../../../docs/framework/app-domains/programming-with-assemblies.md)