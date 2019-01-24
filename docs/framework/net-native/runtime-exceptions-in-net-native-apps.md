---
title: Laufzeitausnahmen in .NET Native-Apps
ms.date: 03/30/2017
ms.assetid: 5f050181-8fdd-4a4e-9d16-f84c22a88a97
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da30ae3f32ebbfabbdf35dd939c27b8d88e7e755
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54696866"
---
# <a name="runtime-exceptions-in-net-native-apps"></a>Laufzeitausnahmen in .NET Native-Apps
Es ist wichtig, die Releasebuilds Ihrer App für die universelle Windows-Plattform auf den Zielplattformen zu testen, da die Debug- und Releasekonfigurationen völlig unterschiedlich sind. Die Debugkonfiguration verwendet standardmäßig die .NET Core-Laufzeit zum Kompilieren der App, während die Releasekonfiguration .NET Native verwendet, um die App in systemeigenen Code zu kompilieren.  
  
> [!IMPORTANT]
>  Informationen zum Umgang mit den [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md), [MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md), und [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) Ausnahmen, die Sie möglicherweise Beim Testen der Releaseversionen Ihrer App auftreten, finden Sie unter "Schritt 4: Manuelles Beheben fehlender Metadaten: in der [Einstieg](../../../docs/framework/net-native/getting-started-with-net-native.md) Thema sowie [Reflektion und .NET Native](../../../docs/framework/net-native/reflection-and-net-native.md) und [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).  
  
## <a name="debug-and-release-builds"></a>Debugbuilds und Releasebuilds  
 Wenn der Debugbuild unter Verwendung der .NET Core-Laufzeit ausgeführt wird, wurde er nicht in systemeigenen Code kompiliert. Dadurch werden alle Dienste, die normalerweise von der Laufzeit bereitgestellt werden, für Ihre App verfügbar.  
  
 Andererseits werden der Releasebuild für die Zielplattformen in systemeigenen Code kompiliert, die meisten Abhängigkeiten von externen Laufzeiten und Bibliotheken entfernt und Code für maximale Leistung optimiert.  
  
 Beim Debuggen von Releasebuilds, die mithilfe von .NET Native kompiliert wurden, geschieht Folgendes:  
  
-   Sie verwenden die .NET Native-Debug-Engine, die sich von den normalen .NET-Debugtools unterscheidet.  
  
-   Die Größe Ihrer ausführbaren Datei wird so weit wie möglich reduziert. Eine der Methoden, durch die .NET Native die Größe einer ausführbaren Datei verringert, besteht darin, dass Laufzeitausnahmemeldungen erheblich gekürzt werden. Dieses Thema wird ausführlicher im Abschnitt [Runtime exception messages](#Messages) erörtert.  
  
-   Der Code wird stark optimiert. Dies bedeutet, dass nach Möglichkeit Inlining verwendet wird. (Beim Inlining wird Code aus externen Routinen in die aufrufende Routine verschoben.)   Die Tatsache, dass .NET Native eine spezielle Laufzeit bietet und aggressives Inlining implementiert, wirkt sich auf die beim Debuggen angezeigte Aufrufliste aus.  Weitere Informationen finden Sie im Abschnitt [Runtime call stack](#CallStack) .  
  
> [!NOTE]
>  Sie können steuern, ob die Debug- und Releasebuilds mit der .NET Native-Toolkette kompiliert werden, indem Sie das Kontrollkästchen **Mit .NET Native-Toolkette kompilieren** aktivieren oder deaktivieren.   Beachten Sie jedoch, dass die Produktionsversion Ihrer App vom Windows Store immer mit der .NET Native-Toolkette kompiliert wird.  
  
<a name="Messages"></a>   
## <a name="runtime-exception-messages"></a>Runtime exception messages  
 Um die Größe ausführbarer Anwendungsdateien zu minimieren, schließt .NET Native nicht den vollständigen Text von Ausnahmemeldungen ein. Daher wird bei Laufzeitausnahmen, die in Releasebuilds ausgelöst werden, u. U. nicht der vollständige Text der Ausnahmemeldungen angezeigt. Stattdessen kann der Text eine Teilzeichenfolge und einen Link umfassen, über den weitere Informationen abgerufen werden können. Beispielsweise können Ausnahmeinformationen wie folgt angezeigt werden:  
  
```  
Exception thrown: '$16_System.AggregateException' in Unknown Module.  
  
Additional information: AggregateException_ctor_DefaultMessage  
  
If there is a handler for this exception, the program may be safely continued.  
```  
  
 Wenn Sie die vollständige Ausnahmemeldung benötigen, führen Sie stattdessen den Debugbuild aus. Beispielsweise könnte die vorherigen Ausnahmeinformationen aus dem Releasebuild im Debugbuild wie folgt aussehen:  
  
```  
Exception thrown: 'System.AggregateException' in NativeApp.exe.  
  
Additional information: Value does not fall within the expected range.  
```  
  
<a name="CallStack"></a>   
## <a name="runtime-call-stack"></a>Runtime call stack  
 Durch das Inlining und andere Optimierungen kann es schwierig sein, den Pfad zu einer Laufzeitausnahme anhand der Aufrufliste, die von einer App angezeigt wird, die von der .NET Native-Toolkette kompiliert wurde, eindeutig zu identifizieren.  
  
 Um die vollständige Aufrufliste zu erhalten, führen Sie stattdessen den Debugbuild aus.  
  
## <a name="see-also"></a>Siehe auch
- [Debuggen von .NET Native Windows Universal-Apps](https://blogs.msdn.com/b/visualstudioalm/archive/2015/07/29/debugging-net-native-windows-universal-apps.aspx)
- [Erste Schritte](../../../docs/framework/net-native/getting-started-with-net-native.md)
