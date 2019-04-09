---
title: invalidIUnknown-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid IUnknown pointer
- InvalidIUnknown MDA
- invalid IUnknown pointers
- IUnknown pointers
- managed debugging assistants (MDAs), invalid IUnknown pointer
ms.assetid: c7924771-a16b-40fe-b337-ce51dcdf6a12
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 35560b966d5fba60ac35b2eb1e559e196fc868f5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223354"
---
# <a name="invalidiunknown-mda"></a>invalidIUnknown-MDA
Der Assistent für verwaltetes Debuggen (Managed Debugging Assistant, MDA) `invalidIUnknown` wird aktiviert, wenn ein `IUnknown`-Zeiger aus dem systemeigenen Code an verwalteten Code übergeben wird. Die Rückgabe einer Erfolgsmeldung durch `IUnknown` schlägt fehl, wenn die `IUnknown`-Schnittstelle abgefragt wird.  
  
## <a name="symptoms"></a>Symptome  
 Beim Marshallen eines COM-Schnittstellenzeigers während des Marshallens von Argumenten tritt ein unerwarteter Fehler auf.  
  
## <a name="cause"></a>Ursache  
 Eine falsche `QueryInterface`-Implementierung der COM-Schnittstelle wurde an die CLR übergeben.  
  
## <a name="resolution"></a>Auflösung  
 Korrigieren Sie die `QueryInterface`-Implementierung.  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die CLR.  
  
## <a name="output"></a>Output  
 Die Beschreibung des Fehlers.  
  
## <a name="configuration"></a>Konfiguration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidIUnknown />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Interop-Marshalling](../../../docs/framework/interop/interop-marshaling.md)
