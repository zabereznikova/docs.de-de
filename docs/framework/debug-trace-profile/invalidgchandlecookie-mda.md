---
title: invalidGCHandleCookie-MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid cookies
- cookies, invalid
- managed debugging assistants (MDAs), invalid cookies
- InvalidGCHandleCookie MDA
- invalid cookies
ms.assetid: 613ad742-3c11-401d-a6b3-893ceb8de4f8
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4757298a382085c1ffebc9a04e41eea81c31941b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="invalidgchandlecookie-mda"></a>invalidGCHandleCookie-MDA
Der `invalidGCHandleCookie`-MDA (Assistent für verwaltetes Debuggen) wird aktiviert, wenn eine Konvertierung von einem ungültigen <xref:System.IntPtr>-Cookie in ein <xref:System.Runtime.InteropServices.GCHandle> versucht wird.  
  
## <a name="symptoms"></a>Symptome  
 Ein nicht definiertes Verhalten, z.B. Zugriffsverletzungen und Speicherschäden, beim Versuch <xref:System.Runtime.InteropServices.GCHandle> aus <xref:System.IntPtr> abzurufen oder zu verwenden.  
  
## <a name="cause"></a>Ursache  
 Das Cookie ist wahrscheinlich ungültig, da es entweder nicht ursprünglich von <xref:System.Runtime.InteropServices.GCHandle> erstellt wurde, <xref:System.Runtime.InteropServices.GCHandle> darstellt, das bereits freigegeben wurde oder ein Cookie für <xref:System.Runtime.InteropServices.GCHandle> in einer anderen Anwendungsdomäne ist. Außerdem könnte es als <xref:System.Runtime.InteropServices.GCHandle> in nativen Code gemarshallt und als <xref:System.IntPtr> in die CLR zurückgegeben worden sein, in der eine Umwandlung versucht wurde.  
  
## <a name="resolution"></a>Auflösung  
 Geben Sie ein gültiges <xref:System.IntPtr>-Cookie für <xref:System.Runtime.InteropServices.GCHandle> an.  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  
 Wenn dieser MDA aktiviert ist, kann der Debugger die Stämme nicht länger zu ihren Objekten zurückverfolgen, da die zurückgegebenen Cookiewerte sich von denjenigen unterscheiden, die zurückgegeben werden, wenn der MDA nicht aktiviert ist.  
  
## <a name="output"></a>Ausgabe  
 Der ungültige <xref:System.IntPtr>-Cookiewert wird gemeldet.  
  
## <a name="configuration"></a>Konfiguration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidGCHandleCookie />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.InteropServices.GCHandle.FromIntPtr%2A>  
 <xref:System.Runtime.InteropServices.GCHandle>  
 [Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
