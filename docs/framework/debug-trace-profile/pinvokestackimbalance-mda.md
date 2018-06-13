---
title: pInvokeStackImbalance-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- signatures, platform invoke
- stack depth
- platform invoke stack imbalance
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- PInvokeStackImbalance MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: 34ddc6bd-1675-4f35-86aa-de1645d5c631
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9938db3f4a3d054fde52139c166fb6a2e2a402df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33388055"
---
# <a name="pinvokestackimbalance-mda"></a>pInvokeStackImbalance-MDA
Der `pInvokeStackImbalance`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn die CLR erkennt, dass die Stapeltiefe nach einem Plattformaufruf nicht mit der Stapeltiefe übereinstimmt, die in Anbetracht der im <xref:System.Runtime.InteropServices.DllImportAttribute>-Attribut angegebenen Aufrufkonvention und der Parameter in der verwalteten Signatur zu erwarten war.  
  
> [!NOTE]
>  Der `pInvokeStackImbalance`-MDA wird nur für 32-Bit-x86-Plattformen implementiert.  
  
> [!NOTE]
>  In .NET Framework, Version 3.5, ist der `pInvokeStackImbalance`-MDA standardmäßig deaktiviert. Wenn Sie .NET Framework, Version 3.5, mit Visual Studio 2005 verwenden, wird der `pInvokeStackImbalance`-MDA in der Liste **Assistenten für verwaltetes Debuggen** im Dialogfeld **Ausnahmen** angezeigt. (Das Dialogfeld wird aufgerufen, wenn Sie im Menü **Debuggen** auf **Ausnahmen** klicken). Wenn Sie jedoch das Kontrollkästchen **Ausgelöst** für `pInvokeStackImbalance` aktivieren oder deaktivieren, wird der MDA nicht aktiviert bzw. deaktiviert; hierdurch wird nur festgelegt, ob Visual Studio beim Aktivieren des MDAs eine Ausnahme auslöst.  
  
## <a name="symptoms"></a>Symptome  
 Während eines Plattformaufrufs in einer Anwendung oder danach kommt es zu einer Zugriffsverletzung oder Speicherbeschädigung.  
  
## <a name="cause"></a>Ursache  
 Die verwaltete Signatur des Plattformaufrufs stimmt möglicherweise nicht mit der nicht verwalteten Signatur der aufgerufenen Methode überein.  Dazu kann es kommen, wenn für die verwaltete Methode nicht die korrekte Anzahl der Parameter bzw. eine falsche Parametergröße deklariert wurde.  Der MDA wird auch aktiviert, wenn die ggf. durch das <xref:System.Runtime.InteropServices.DllImportAttribute>-Attribut festgelegte Aufrufkonvention nicht mit der nicht verwalteten Aufrufkonvention übereinstimmt.  
  
## <a name="resolution"></a>Lösung  
 Überprüfen Sie die Signatur des verwalteten Plattformaufrufs sowie die Aufrufkonvention, um sich zu vergewissern, dass diese mit der Signatur und Aufrufkonvention des systemeigenen Ziels übereinstimmen.  Versuchen Sie, die Aufrufkonvention sowohl auf der verwalteten als auch auf der nicht verwalteten Seite explizit anzugeben. Es ist ebenfalls möglich (wenn auch weniger wahrscheinlich), dass die nicht verwaltete Funktion aus einem anderen Grund einen nicht ausgeglichenen Stapel verursacht hat, beispielsweise durch einen Programmfehler im nicht verwalteten Compiler.   
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  
 Erzwingt für alle Plattformaufrufe die Verwendung des nicht optimierten Pfads in die CLR.  
  
## <a name="output"></a>Ausgabe  
 Die MDA-Meldung enthält den Namen der Plattformaufrufmethode, die das Stapelungleichgewicht verursacht hat.  Beispielmeldung eines Plattformaufrufs der `SampleMethod`-Methode:   
  
```  
A call to PInvoke function 'SampleMethod' has unbalanced the stack.   
This is likely because the managed PInvoke signature does not match   
the unmanaged target signature. Check that the calling convention and   
parameters of the PInvoke signature match the target unmanaged signature.  
```  
  
## <a name="configuration"></a>Konfiguration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <pInvokeStackImbalance />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [Interop Marshaling (Interop-Marshalling)](../../../docs/framework/interop/interop-marshaling.md)
