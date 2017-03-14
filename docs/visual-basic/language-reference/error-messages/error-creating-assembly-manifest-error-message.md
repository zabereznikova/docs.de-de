---
title: "Error creating assembly manifest: &lt;error message&gt; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30140"
  - "vbc30140"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30140"
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Error creating assembly manifest: &lt;error message&gt;
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Der [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]\-Compiler ruft den Assemblylinker \(Al.exe, auch bekannt als Alink\) auf, um eine Assembly mit einem Manifest zu erstellen.  Der Linker meldet einen Fehler in der Vorausgabestufe der Assemblyerstellung.  
  
 Zu diesem Fehler kann es kommen, wenn es Probleme mit der angegebenen Schlüsseldatei oder dem angegebenen Schlüsselcontainer gibt.  Um eine Assembly vollständig zu signieren, müssen Sie eine gültige Schlüsseldatei bereitstellen, die Informationen zu den öffentlichen und privaten Schlüsseln enthält.  Um das Signieren einer Assembly zu verzögern, müssen Sie das Kontrollkästchen **Nur verzögerte Signierung** aktivieren und eine gültige Schlüsseldatei angeben, die Informationen zum öffentlichen Schlüssel enthält.  Der private Schlüssel ist nicht erforderlich, wenn eine Assembly verzögert signiert wird.  Weitere Informationen finden Sie unter [How to: Sign an Assembly \(Visual Studio\)](http://msdn.microsoft.com/de-de/f468a7d3-234c-4353-924d-8e0ae5896564).  
  
 **Fehler\-ID:** BC30140  
  
### So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie die angegebene Fehlermeldung, und gehen Sie zum Thema [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/de-de/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) zum Fehler AL1019, um weitere Erläuterungen und Hinweise zu erhalten.  
  
2.  Wenn der Fehler weiterhin besteht, tragen Sie Informationen zu den Umständen zusammen, und benachrichtigen Sie den Produktsupport von Microsoft.  
  
## Siehe auch  
 [How to: Sign an Assembly \(Visual Studio\)](http://msdn.microsoft.com/de-de/f468a7d3-234c-4353-924d-8e0ae5896564)   
 [Seite "Signierung", Projekt\-Designer](/visual-studio/ide/reference/signing-page-project-designer)   
 [Al.exe \(Assembly Linker\-Tool\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)   
 [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/de-de/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)   
 [Sprechen Sie mit uns](/visual-studio/ide/talk-to-us)