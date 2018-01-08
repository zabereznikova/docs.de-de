---
title: 'Gewusst wie: Entfernen einer Assembly aus dem globalen Assemblycache'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- global assembly cache, removing assemblies
- strong-named assemblies, global assembly cache
- removing assemblies from global assembly cache
- deleting assemblies in global assembly cache
- Global Assembly Cache tool
- GAC (global assembly cache), removing assemblies
ms.assetid: acdcc588-b458-436d-876c-726de68244c1
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5d50d6a1b27cf30511fece1540f002524238a424
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-remove-an-assembly-from-the-global-assembly-cache"></a>Gewusst wie: Entfernen einer Assembly aus dem globalen Assemblycache
Es gibt zwei Möglichkeiten, eine Assembly aus dem globalen Assemblycache (GAC) zu entfernen:  
  
-   Durch Verwenden des [Global Assembly Cache-Tools (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md). Diese Option können Sie zum Deinstallieren von Assemblys verwenden, die Sie beim Entwickeln und Testen im GAC platziert haben.  
  
-   Mithilfe von [Windows Installer](http://msdn.microsoft.com/library/windows/desktop/cc185688.aspx). Diese Option für das Deinstallieren von Assemblys sollten Sie für Produktionssysteme und dann verwenden, wenn Sie Installationspakete testen.  
  
### <a name="removing-an-assembly-with-gacutilexe"></a>Entfernen einer Assembly mit "Gacutil.exe"  
  
1.  Geben Sie an der Eingabeaufforderung folgenden Befehl ein:  
  
     **gacutil –u** \<*assemblyname*>  
  
     In diesem Befehl ist *Assemblyname* der Name der Assembly, die aus dem globalen Assemblycache entfernt werden soll.  
  
    > [!WARNING]
    >  Sie sollten "Gacutil.exe" nicht verwenden, um Assemblys auf Produktionssystemen zu entfernen, denn es besteht die Möglichkeit, dass die Assembly für einige Anwendungen weiterhin erforderlich ist. Stattdessen sollten Sie den Windows Installer verwenden, der einen Verweiszähler für jede Assembly verwaltet, die er im GAC installiert.  
  
 Im folgenden Beispiel wird die Assembly `hello.dll` aus dem globalen Assemblycache entfernt.  
  
```  
gacutil -u hello  
```  
  
### <a name="removing-an-assembly-with-windows-installer"></a>Entfernen einer Assembly mit Windows Installer  
  
1.  Wählen Sie in der **Systemsteuerung** in **Programme und Funktionen** die Anwendung aus, die Sie deinstallieren möchten. Wenn das Installationspaket Assemblys im GAC platziert hat, werden diese von Windows Installer entfernt, sofern sie nicht von einer anderen Anwendung verwendet werden.  
  
    > [!NOTE]
    >  Windows Installer verwaltet einen Verweiszähler für Assemblys, die im GAC installiert sind. Eine Assembly wird nur dann aus dem GAC entfernt, wenn ihr Verweiszähler gleich null wird, wodurch angegeben ist, dass sie von keiner der Anwendungen verwendet wird, die über ein Windows Installer-Paket installiert wurden.  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit Assemblys und dem globalen Assemblychache](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [Gewusst wie: Installieren einer Assembly in den globalen Assemblycache](../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)  
 [Gacutil.exe (Global Assembly Cache-Tool)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
