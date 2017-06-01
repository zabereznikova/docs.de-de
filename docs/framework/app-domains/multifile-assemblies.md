---
title: "Mehrfachdateiassemblys | Microsoft Docs"
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
  - "Assemblys [.NET Framework], Mehrfachdatei"
  - "Assemblymanifest, Mehrfachdateiassemblys"
  - "Codemodule"
  - "Befehlszeilencompiler"
  - "Kompilieren von Assemblys"
  - "Einsprungpunkt für Assembly"
  - "Mehrfachdateiassemblys"
ms.assetid: 13509e73-db77-4645-8165-aad8dfaedff6
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Mehrfachdateiassemblys
Sie können Mehrfachdateiassemblys mit Befehlszeilencompilern oder unter Verwendung von [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] mit Visual C\+\+ erstellen.  Eine Datei der Assembly muss das Assemblymanifest enthalten.  Eine Assembly, die eine Anwendung startet, muss einen Einstiegspunkt enthalten, z. B. die Main\-Methode oder die WinMain\-Methode.  
  
 Angenommen, Sie verfügen über eine Anwendung mit zwei Codemodulen: Client.cs und Stringer.cs.  Stringer.cs erstellt den `myStringer`\-Namespace, auf den vom Code in Client.cs verwiesen wird.  Client.cs enthält die `Main`\-Methode, die den Einstiegspunkt der Anwendung darstellt.  In diesem Beispiel kompilieren Sie die beiden Codemodule und erstellen anschließend eine dritte Datei, die das Assemblymanifest zum Starten der Anwendung enthält.  Das Assemblymanifest verweist sowohl auf das `Client`\-Modul als auch auf das `Stringer`\-Modul.  
  
> [!NOTE]
>  Mehrfachdateiassemblys können nur einen Einstiegspunkt aufweisen, selbst wenn die Assembly mehrere Codemodule umfasst.  
  
 Es gibt mehrere Gründe, eine Mehrfachdateiassembly zu erstellen:  
  
-   Kombinieren von Modulen, die in verschiedenen Sprachen geschrieben wurden.  Dies ist der häufigste Anlass für das Erstellen einer Mehrfachdateiassembly.  
  
-   Optimieren des Herunterladens einer Anwendung, indem selten verwendete Typen in einem Modul platziert werden, das nur bei Bedarf heruntergeladen wird.  
  
    > [!NOTE]
    >  Es ist wichtig, Mehrfachdateiassemblys einzusetzen, wenn Sie Anwendungen erstellen, die mit dem `<object>`\-Tag von Microsoft Internet Explorer heruntergeladen werden sollen.  In diesem Szenario erstellen Sie eine von den Codemodulen unabhängige Datei, die nur das Assemblymanifest enthält.  Internet Explorer lädt zuerst das Assemblymanifest herunter und erstellt anschließend Arbeitsthreads zum Herunterladen aller weiteren benötigten Module und Assemblys.  Während des Herunterladens der Datei, die das Assemblymanifest enthält, reagiert Internet Explorer nicht auf Benutzereingaben.  Je kleiner diese Datei ist, desto weniger Zeit nimmt dies in Anspruch.  
  
-   Kombinieren von Codemodulen, die von verschiedenen Entwicklern geschrieben wurden.  Jeder Entwickler kann im Prinzip jedes beliebige Codemodul in eine Assembly kompilieren. Dies kann jedoch dazu führen, dass einige Typen öffentlich verfügbar gemacht werden müssen, was verhindert werden kann, indem alle Module in einer Mehrfachdateiassembly untergebracht werden.  
  
 Nachdem Sie eine Assembly erstellt haben, können Sie die Datei signieren, die das Assemblymanifest \(und somit die Assembly\) enthält. Alternativ können Sie der Datei \(und der Assembly\) einen starken Namen geben und sie im globalen Assemblycache ablegen.  
  
## Siehe auch  
 [Gewusst wie: Erstellen einer Mehrfachdateiassembly](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)   
 [Programmieren mit Assemblys](../../../docs/framework/app-domains/programming-with-assemblies.md)