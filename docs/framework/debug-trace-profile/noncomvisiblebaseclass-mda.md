---
title: NonComVisibleBaseClass-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- visible classes
- managed debugging assistants (MDAs), COM visible classes
- nonComVisibleBaseClass MDA
- COM visible classes
- QueryInterface call failures
- MDAs (managed debugging assistants), COM visible classes
ms.assetid: 9ec1af27-604b-477e-9ee2-e833eb10d3ce
ms.openlocfilehash: b46d5c6ffbf12efbae113a95bbfccd5742ec9ec9
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217301"
---
# <a name="noncomvisiblebaseclass-mda"></a>NonComVisibleBaseClass-MDA
Der `nonComVisibleBaseClass`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn durch systemeigenen oder nicht verwalteten Code ein `QueryInterface`-Aufruf für den COM Callable Wrapper (CCW) einer für COM sichtbaren verwalteten Klasse erfolgt, die von einer für COM nicht sichtbaren Basisklasse abgeleitet ist.  Der `QueryInterface`-Aufruf führt nur in den Fällen zur Aktivierung des MDA, in denen der Aufruf die Klassenschnittstelle oder die `IDispatch`-Standardschnittstelle der für COM sichtbaren verwalteten Klasse anfordert.  Der MDA wird nicht aktiviert, wenn mit dem `QueryInterface`-Aufruf eine explizite Schnittstelle angefordert wird, auf die das <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>-Attribut angewendet wurde und die von der für COM sichtbaren Klasse explizit implementiert wird.  
  
## <a name="symptoms"></a>Symptome  
 Ein `QueryInterface`-Aufruf von systemeigenem Code, der zu einem HRESULT COR_E_INVALIDOPERATION führt.  Das HRESULT ist möglicherweise darauf zurückzuführen, dass die Laufzeit keine `QueryInterface`-Aufrufe zulässt, die zur Aktivierung dieses MDA führen würden.  
  
## <a name="cause"></a>Ursache  
 Aufgrund von potenziellen Versionsproblemen kann die Laufzeit keine `QueryInterface`-Aufrufe für die Klassenschnittstelle oder für die `IDispatch`-Standardschnittstelle einer für COM sichtbaren Klasse zulassen, die von einer für COM nicht sichtbaren Klasse abgeleitet ist.  Beispiel: Falls der für COM nicht sichtbaren Basisklasse öffentliche Member hinzugefügt würden, könnten vorhandene COM-Clients, die die abgeleitete Klasse verwenden, beschädigt werden, weil die vtable der abgeleiteten Klasse, die die Member der Basisklasse enthält, hierbei geändert würde.  Bei expliziten Schnittstellen, die für COM verfügbar gemacht wurden, tritt dieses Problem nicht auf, weil deren vtable die Basismember der Schnittstellen nicht enthält.  
  
## <a name="resolution"></a>Lösung  
 Machen Sie die Klassenschnittstelle nicht verfügbar. Definieren Sie eine explizite Schnittstelle, und wenden Sie das <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>-Attribut auf die Schnittstelle an.  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die CLR.  
  
## <a name="output"></a>Output  
 Im Folgenden finden Sie eine Beispielmeldung für einen `QueryInterface`-Aufruf für die für COM sichtbare `Derived`-Klasse, die von der für COM nicht sichtbaren `Base`-Klasse abgeleitet ist.  
  
```output
A QueryInterface call was made requesting the class interface of COM   
visible managed class 'Derived'. However since this class derives from   
non COM visible class 'Base', the QueryInterface call will fail. This   
is done to prevent the non COM visible base class from being   
constrained by the COM versioning rules.   
```  
  
## <a name="configuration"></a>Konfiguration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <nonComVisibleBaseClass />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnosing Errors with Managed Debugging Assistants (Fehlerdiagnose mit den Assistenten für verwaltetes Debugging)](diagnosing-errors-with-managed-debugging-assistants.md)
- [Interop Marshaling (Interop-Marshalling)](../interop/interop-marshaling.md)
