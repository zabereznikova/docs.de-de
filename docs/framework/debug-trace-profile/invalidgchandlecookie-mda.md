---
title: invalidGCHandleCookie-MDA
description: Überprüfen Sie den invalidGCHandleCookie-MDA (Managed Debugging Assistant), der aktiviert wird, wenn eine Konvertierung von einem ungültigen IntPtr-Cookie in ein GCHandle versucht wird.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid cookies
- cookies, invalid
- managed debugging assistants (MDAs), invalid cookies
- InvalidGCHandleCookie MDA
- invalid cookies
ms.assetid: 613ad742-3c11-401d-a6b3-893ceb8de4f8
ms.openlocfilehash: 1063b7be902d3063717b6639564d819ef3292c0e
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051297"
---
# <a name="invalidgchandlecookie-mda"></a>invalidGCHandleCookie-MDA
Der `invalidGCHandleCookie`-MDA (Assistent für verwaltetes Debuggen) wird aktiviert, wenn eine Konvertierung von einem ungültigen <xref:System.IntPtr>-Cookie in ein <xref:System.Runtime.InteropServices.GCHandle> versucht wird.  
  
## <a name="symptoms"></a>Symptome  
 Ein nicht definiertes Verhalten, z.B. Zugriffsverletzungen und Speicherschäden, beim Versuch <xref:System.Runtime.InteropServices.GCHandle> aus <xref:System.IntPtr> abzurufen oder zu verwenden.  
  
## <a name="cause"></a>Ursache  
 Das Cookie ist wahrscheinlich ungültig, da es entweder nicht ursprünglich von <xref:System.Runtime.InteropServices.GCHandle> erstellt wurde, <xref:System.Runtime.InteropServices.GCHandle> darstellt, das bereits freigegeben wurde oder ein Cookie für <xref:System.Runtime.InteropServices.GCHandle> in einer anderen Anwendungsdomäne ist. Außerdem könnte es als <xref:System.Runtime.InteropServices.GCHandle> in nativen Code gemarshallt und als <xref:System.IntPtr> in die CLR zurückgegeben worden sein, in der eine Umwandlung versucht wurde.  
  
## <a name="resolution"></a>Lösung  
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

- <xref:System.Runtime.InteropServices.GCHandle.FromIntPtr%2A>
- <xref:System.Runtime.InteropServices.GCHandle>
- [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](diagnosing-errors-with-managed-debugging-assistants.md)
