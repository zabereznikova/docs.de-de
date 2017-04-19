---
title: Veraltete Elemente in der .NET Framework-Klassenbibliothek | Microsoft-Dokumentation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- obsolete [.NET Framework]
- what's obsolete [.NET Framework]
- deprecated [.NET Framework]
ms.assetid: d356a43a-73df-4ae2-a457-b9628074c7cd
caps.latest.revision: 19
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 68c71e26ac5e5a1872ac006d02adec84c1fb63da
ms.lasthandoff: 04/18/2017

---
# <a name="what39s-obsolete-in-the-net-framework-class-library"></a>Veraltete Elemente in der .NET Framework-Klassenbibliothek
.NET Framework unterliegt im Laufe der Zeit Änderungen. Jede neue Version erhält neue Typen und Typmember, die neue Funktionen bieten. Vorhandene Typen und deren Member werden im Laufe der Zeit ebenfalls geändert. Einige Typen verlieren z. B. an Bedeutung, da die von ihnen unterstützte Technologie durch eine neue Technologie ersetzt wird, und einige Methoden werden von neueren Methoden abgelöst, die entweder benutzerfreundlicher sind oder über einen größeren Funktionsumfang verfügen.  
  
 .NET Framework und die Common Language Runtime sollen Abwärtskompatibilität unterstützen (dadurch können Anwendungen, die mit einer bestimmten Version von .NET Framework entwickelt wurden, unter der nächsten Version von .NET Framework ausgeführt werden). Dadurch wird es schwierig, einfach einen Typ oder einen Typmember zu entfernen. Stattdessen gibt .NET Framework an, dass ein Typ oder Typmember nicht mehr verwendet werden sollte, indem er als veraltet markiert wird. Ein veralteter Typ oder Member muss entsprechend markiert werden, damit Entwickler Bescheid wissen, dass er entfernt werden soll und die Zeit haben, auf das Entfernen des Typs zu reagieren. Allerdings wird vorhandener Code, in dem der Typ oder Member verwendet wird, weiterhin in der neuen Version von .NET Framework ausgeführt.  
  
> [!NOTE]
>  Die Begriffe *veraltet* und *nicht mehr aktuell* haben die gleiche Bedeutung, wenn sie in Bezug auf die Typen und Member von .NET Framework angewendet werden.  
  
## <a name="the-obsoleteattribute-attribute"></a>Das ObsoleteAttribute-Attribut  
 .NET Framework gibt an, dass ein Typ oder ein Typmember veraltet ist, indem er mit dem <xref:System.ObsoleteAttribute>-Attribut markiert wird. Das Anwenden des Attributs auf einen Typ oder Member gibt an, dass der Typ oder Member in einer künftigen Version von .NET Framework entfernt wird, ohne dass kompilierter Code in Mitleidenschaft gezogen wird, der diesen Member verwendet.  
  
 Neben der Angabe, dass ein Typ oder Typmember veraltet ist, wird mit <xref:System.ObsoleteAttribute> definiert, wie der Compiler Quellcode behandelt, der den Typ oder Member enthält. Der Compiler kann den Code kompilieren, aber eine Warnmeldung ausgeben, oder er kann die Verwendung des Typs oder Members als Fehler behandeln. Im ersten Fall kann der Code kompiliert werden, doch eine Warnmeldung zeigt an, dass der Typ oder der Member veraltet ist. Im zweiten Fall schlägt die Kompilierung fehl.  
  
 Auch wenn bei einer Kompilierung keine Warnmeldung angezeigt wird, sondern ein Fehler auftritt, wirkt sich <xref:System.ObsoleteAttribute> nicht auf das Laufzeitverhalten aus. Das heißt, dass Anwendungen, die den Typ oder den Member verwenden und die kompiliert wurden, immer ausgeführt werden. Nur der Versuch der erneuten Kompilierung einer Anwendung, die den Typ oder Member verwendet, schlägt fehl.  
  
## <a name="how-to-handle-obsolete-types-and-members"></a>Behandeln von veralteten Typen und Membern  
 Wenn Sie vorhandenen Code aktualisieren und neu kompilieren, kann ohne weiteres ein veralteter Typ oder Member verwendet werden, durch den eine Compilerwarnung in der Anwendung erzeugt wird. Lesen Sie jedoch die Compilerwarnungsmeldung, um festzustellen, ob der Anwendungscode geändert werden sollte. Wenn in der Meldung nicht auf eine geeignete Alternative hingewiesen wird, führen Sie einen der folgenden Schritte aus:  
  
-   Ändern Sie, falls möglich, den Code durch Entfernen der Verwendung des Typs oder des Members.  
  
     - oder -   
  
-   Lesen Sie die Dokumentation für diesen Technologiebereich, um zu bestimmen, wie darauf reagiert werden soll, dass die Komponente veraltet ist.  
  
 Sie können sich dazu entscheiden, keinen vorhandenen Code für eine höhere Version von .NET Framework neu zu kompilieren. Stattdessen können Sie die Version von .NET Framework angeben, für die der vorhandene kompilierte Code ausgeführt wird. Beispiel: Angenommen, Sie besitzen eine Anwendung mit dem Namen "app1.exe", die für [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] kompiliert wurde, doch Sie möchten, dass die Anwendung für [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] ausgeführt wird. Gehen Sie dazu folgendermaßen vor:  
  
1.  Erstellen Sie eine Konfigurationsdatei für die zentrale ausführbare Datei, und nennen Sie diese *appName*.exe.config, wobei *appName* der Name der ausführbaren Datei der Anwendung ist. Für die Anwendung mit dem Namen "app1.exe" in diesem Beispiel würden Sie eine Konfigurationsdatei mit dem Namen "app1.exe.config" erstellen.  
  
2.  Fügen Sie der Konfigurationsdatei Folgendes hinzu:  
  
    ```  
    <configuration>  
       <startup>   
          <supportedRuntime version="v4.0" />  
       </startup>  
    </configuration>  
    ```  
  
 In der folgenden Tabelle sind die Zeichenfolgenwerte aufgeführt, die Sie dem `version`-Attribut zuweisen können, um eine bestimmte Version von .NET Framework als Zielversion festzulegen.  
  
|.NET Framework-Version|`version`-Zeichenfolge|
|-|-|  
|4.7|v4.0|  
|4.6 (einschließlich 4.6.1 und 4.6.2)|v4.0|  
|4.5 (inklusive 4.5.1 und 4.5.2)|v4.0|  
|4|v4.0|  
|3.5|v2.0.50727|  
|2.0|v2.0.50727|  
|1.1|v1.1.4322|  
|1.0|v1.0.3705|  
  
## <a name="obsolete-lists-for-the-net-framework-45-and-46"></a>Listen mit veralteten Komponenten für .NET Framework 4.5 und 4.6  
 [Veraltete Typen](../../../docs/framework/whats-new/obsolete-types.md)  
  
 [Veraltete Member](../../../docs/framework/whats-new/obsolete-members.md)  
  
## <a name="obsolete-lists-for-previous-versions"></a>Listen mit veralteten Komponenten für frühere Versionen  
 [Veraltete Typen in .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=224224)  
  
 [Veraltete Member in .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=224227)  
  
 [Liste veralteter Elemente in .NET Framework 3.5](http://go.microsoft.com/fwlink/?LinkId=163710)  
  
 [Liste veralteter Elemente in .NET Framework 2.0](http://go.microsoft.com/fwlink/?LinkID=125264)  
  
## <a name="see-also"></a>Siehe auch  
 [\<supportedRuntime> Element](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)
