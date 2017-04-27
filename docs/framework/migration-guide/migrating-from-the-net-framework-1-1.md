---
title: Migrieren von .NET Framework 1.1 | Microsoft-Dokumentation
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
- .NET Framework 4.5, migrating from 1.1
- .NET Framework 1.1, migrating to .NET Framework 4.5
ms.assetid: 7ead0cb3-3b19-414a-8417-a1c1fa198d9e
caps.latest.revision: 12
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6a9df183b13a84f8ded047892c0e4b7f7d5f0d60
ms.lasthandoff: 04/18/2017

---
# <a name="migrating-from-the-net-framework-11"></a>Migrieren von .NET Framework 1.1
[!INCLUDE[win7](../../../includes/win7-md.md)] und neuere Versionen des Windows-Betriebssystems unterstützen [!INCLUDE[net_v11_long](../../../includes/net-v11-long-md.md)] nicht. Folglich können Anwendungen, die auf [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] ausgerichtet sind, unter [!INCLUDE[win7](../../../includes/win7-md.md)] oder neueren Betriebssystemversionen nicht ohne Änderung ausgeführt werden. In diesem Thema werden die Schritte zum Ausführen einer Anwendung erläutert, die auf [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] unter [!INCLUDE[win7](../../../includes/win7-md.md)] und neueren Versionen des Windows-Betriebssystems ausgerichtet ist. Weitere Informationen zu [!INCLUDE[net_v11_long](../../../includes/net-v11-long-md.md)] und [!INCLUDE[win8](../../../includes/win8-md.md)] finden Sie unter [Ausführen von .NET Framework 1.1-Apps unter Windows 8 und späteren Versionen](../../../docs/framework/install/run-net-framework-1-1-apps.md).  
  
## <a name="retargeting-or-recompiling"></a>Zuweisen einer neuen Zielversion oder Neukompilieren  
 Es gibt zwei Möglichkeiten, eine mit [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] kompilierte Anwendung unter [!INCLUDE[win7](../../../includes/win7-md.md)] oder neueren Versionen des Windows-Betriebssystems auszuführen:  
  
-   Sie können der Anwendung [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] als neue Zielversion zuweisen. Für die Zuweisung einer neuen Zielversion müssen Sie der Konfigurationsdatei der Anwendung, die das Ausführen unter [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] ermöglicht, ein [\<supportedRuntime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)-Element hinzufügen. Diese Konfigurationsdatei besitzt das folgende Format:  
  
    ```  
    <configuration>   
       <startup>  
          <supportedRuntime version="v4.0"/>  
       </startup>  
    </configuration>  
  
    ```  
  
-   Sie können die Anwendung mit einem Compiler, der auf [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] ausgerichtet ist, neu kompilieren. Wenn Sie ursprünglich Visual Studio 2003 zum Entwickeln und Kompilieren Ihrer Projektmappe verwendet haben, können Sie die Projektmappe in [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)] öffnen. Die Projektmappe und die Projektdateien können dann über das Dialogfeld **Projektkompatibilität** aus den von Visual Studio 2003 verwendeten Formaten in das Format von Microsoft Build Engine (MSBuild) konvertiert werden, das von [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)]verwendet wird.  
  
 Unabhängig davon, ob Sie eine Neukompilierung oder eine neue Zielversion für die Anwendung vorziehen, müssen Sie bestimmen, ob die Anwendung von Änderungen betroffen ist, die in höheren Versionen von .NET Framework eingeführt wurden. Diese Änderungen sind von zweierlei Art:  
  
-   Änderungen zwischen [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] und höheren Versionen von .NET Framework, die die Lauffähigkeit der Anwendung beeinträchtigen.  
  
-   Typen und Typmember, die zwischen [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] und höheren Versionen von .NET Framework als veraltet markiert wurden.  
  
 Überprüfen Sie beim Zuweisen einer neuen Zielversion und auch beim Neukompilieren sowohl die Änderungen, die die Lauffähigkeit der Anwendung beeinträchtigen, als auch die veralteten Typen und Member für jede Version von .NET Framework, die nach [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] veröffentlicht wurde.  
  
## <a name="breaking-changes"></a>Die Lauffähigkeit der Anwendung beeinträchtigende Änderungen  
 Bei einer Änderung, die die Lauffähigkeit der Anwendung beeinträchtigt, ist ggf. eine Problemumgehung sowohl für Anwendungen mit neuer Zielversion als auch für neu kompilierte Anwendungen verfügbar. In einigen Fällen können Sie dem [\<runtime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)-Element der Konfigurationsdatei der Anwendung ein untergeordnetes Element hinzufügen, um das vorherige Verhalten wiederherzustellen. Die folgende Konfigurationsdatei stellt z. B. die in [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] verwendete Zeichenfolgensortierung und das Vergleichsverhalten wieder her und kann bei neu zugewiesener Zielversion oder einer neu kompilierten Anwendung verwendet werden.  
  
```  
<configuration>  
   <runtime>  
      <CompatSortNLSVersion enabled="4096"/>  
   </runtime>  
</configuration>  
  
```  
  
 In einigen Fällen müssen Sie jedoch möglicherweise den Quellcode ändern und die Anwendung neu kompilieren.  
  
 Überprüfen Sie die folgende Änderungsliste, um die Auswirkungen möglicher Änderungen zu bewerten, die die Lauffähigkeit der Anwendung beeinträchtigen:  
  
-   Unter[Breaking Changes in .NET Framework 2.0](http://go.microsoft.com/fwlink/?LinkId=125263) werden Änderungen in [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)] erläutert, die Auswirkungen auf eine Anwendung für [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] haben können.  
  
-   Unter[Changes in .NET Framework 3.5 SP1](http://go.microsoft.com/fwlink/?LinkID=186989) werden Änderungen zwischen [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] und [!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)]dokumentiert.  
  
-   Unter[Migrationsprobleme in .NET Framework 4](http://msdn.microsoft.com/library/ee941656\(v=vs.100\).aspx) werden Änderungen zwischen [!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)] und [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]dokumentiert.  
  
## <a name="obsolete-types-and-members"></a>Veraltete Typen und Member  
 Die Auswirkungen veralteter Typen und Member unterscheiden sich geringfügig bei Anwendungen mit neu zugewiesener Zielversion und neu kompilierten Anwendungen. Die Verwendung veralteter Typen und Member wirkt sich nicht auf eine Anwendung mit neuer Zielversion aus, sofern der veraltete Typ oder Member nicht physisch aus seiner Assembly entfernt wurde. Das Neukompilieren eine Anwendung, die veraltete Typen oder Member verwendet, erzeugt in der Regel eher eine Compilerwarnung als einen Compilerfehler. In einigen Fällen wird jedoch ein Compilerfehler verursacht, und Code, in dem der veraltete Typ oder Member verwendet wird, kann nicht erfolgreich kompiliert werden. Sie müssen dann den Quellcode neu schreiben, der den veralteten Typ oder Member aufruft, bevor Sie die Anwendung neu kompilieren. Weitere Informationen zu veralteten Typen und Membern finden Sie unter [Veraltete Elemente in der Klassenbibliothek](../../../docs/framework/whats-new/whats-obsolete.md).  
  
 Nähere Informationen zur Bewertung der Auswirkungen von Typen und Membern, die seit dem Release von [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)] veraltet sind, finden Sie unter [Veraltete Elemente in der Klassenbibliothek](../../../docs/framework/whats-new/whats-obsolete.md). Überprüfen Sie die Listen der veralteten Typen und Member für [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)], [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] und [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].
