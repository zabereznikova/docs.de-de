---
title: ReleaseHandleFailed-MDA
description: Überprüfen Sie den ReleaseHandleFailed-MDA (Managed Debugging Assistant), der aufgrund von Ressourcen-oder Speicher Verlusten in .NET aktiviert werden kann.
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), handles
- release handle failed
- CriticalHandle class, run-time errors
- releaseHandleFailed MDA
- ReleaseHandle method
- SafeHandle class, run-time errors
- MDAs (managed debugging assistants), handles
ms.assetid: 44cd98ba-95e5-40a1-874d-e8e163612c51
ms.openlocfilehash: 167a304b4571aa35f758a2054caf6ae1c60a3c60
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803637"
---
# <a name="releasehandlefailed-mda"></a>ReleaseHandleFailed-MDA
Der `releaseHandleFailed`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, um einen Entwickler zu benachrichtigen, wenn die <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A>-Methode einer Klasse, die aus <xref:System.Runtime.InteropServices.SafeHandle> oder <xref:System.Runtime.InteropServices.CriticalHandle> abgeleitet wurde, `false` zurückgibt.  
  
## <a name="symptoms"></a>Symptome  
 Ressourcen- oder Arbeitsspeicherverluste.  Wenn die <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A>-Methode der aus <xref:System.Runtime.InteropServices.SafeHandle> oder <xref:System.Runtime.InteropServices.CriticalHandle> abgeleiteten Klasse fehlschlägt, wurde die durch die Klasse gekapselte Ressource möglicherweise nicht freigegeben oder bereinigt.  
  
## <a name="cause"></a>Ursache  
 Benutzer müssen die Implementierung der <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A>-Methode bereitstellen, wenn sie Klassen erstellen, die aus <xref:System.Runtime.InteropServices.SafeHandle> oder <xref:System.Runtime.InteropServices.CriticalHandle> abgeleitet sind. Daher hängen die Umstände von der jeweiligen Ressource ab. Die Anforderungen sehen jedoch wie folgt aus:  
  
- <xref:System.Runtime.InteropServices.SafeHandle>- und <xref:System.Runtime.InteropServices.CriticalHandle>-Typen sind Wrapper für entscheidende Prozessressourcen. Ein Arbeitsspeicherverlust würde den Prozess im Lauf der Zeit unbrauchbar machen.  
  
- Die <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A>-Methode darf beim Ausführen ihrer Funktion nicht fehlschlagen. Sobald ein Prozess eine solche Ressource abgerufen hat, ist <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> die einzige Möglichkeit, diese freizugeben. Ein Fehlschlagen bedeutet deshalb Ressourcenverluste.  
  
- Jeder Fehler, der während der Ausführung von <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> auftritt und die Freigabe der Ressource verhindert, ist ein Fehler in der Implementierung der <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A>-Methode. Es liegt in der Verantwortung des Programmierers, die Erfüllung des Vertrags sicherzustellen, selbst wenn im Code anderer Code aufgerufen wird, für den eine andere Person die Autorisierung erteilt hat, dessen Funktion auszuführen.  
  
## <a name="resolution"></a>Lösung  
 Überprüfen Sie den Code, in dem der spezielle <xref:System.Runtime.InteropServices.SafeHandle>-Typ (oder <xref:System.Runtime.InteropServices.CriticalHandle>-Typ) verwendet wird, der die MDA-Benachrichtigung ausgelöst hat. Suchen Sie nach Stellen, an denen der unformatierte Handlewert aus dem <xref:System.Runtime.InteropServices.SafeHandle>-Objekt extrahiert und an eine andere Stelle Ort kopiert wird. Hier liegt meist der Grund für Fehler in <xref:System.Runtime.InteropServices.SafeHandle>- oder <xref:System.Runtime.InteropServices.CriticalHandle>-Implementierungen, denn die Verwendung des unformatierten Handlewerts wird dann nicht mehr von der Laufzeitumgebung verfolgt. Wenn die Kopie des unformatierten Handles anschließend geschlossen wird, kann dies dazu führen, dass ein späterer <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A>-Aufruf fehlschlägt, weil versucht wird, dasselbe Handle zu schließen, das jetzt ungültig ist.  
  
 Es gibt eine Reihe von Möglichkeiten, die in denen eine fehlerhafte Handleduplizierung auftreten kann:  
  
- Suchen Sie nach Aufrufen der <xref:System.Runtime.InteropServices.SafeHandle.DangerousGetHandle%2A>-Methode. Diese Methode sollte äußerst selten aufgerufen werden, und jeder Aufruf muss durch Aufrufe der <xref:System.Runtime.InteropServices.SafeHandle.DangerousAddRef%2A>- und der <xref:System.Runtime.InteropServices.SafeHandle.DangerousRelease%2A>-Methode umschlossen sein. Diese beiden Methoden geben den Codebereich an, in dem der unformatierte Handlewert sicher verwendet werden kann. Außerhalb dieses Bereichs, oder wenn die Verweisanzahl nie von vornherein erhöht wird, kann der Handlewert jederzeit durch einen Aufruf von <xref:System.Runtime.InteropServices.SafeHandle.Dispose%2A> oder <xref:System.Runtime.InteropServices.SafeHandle.Close%2A> in einem anderen Thread ungültig gemacht werden. Nachdem Sie alle Vorkommen von <xref:System.Runtime.InteropServices.SafeHandle.DangerousGetHandle%2A> ermittelt haben, folgen Sie dem Weg des unformatierten Handles, um sich zu vergewissern, dass es nicht an eine Komponente übergeben wird, die später `CloseHandle` oder eine andere systemnahe Methode aufruft, in der das Handle freigegeben wird.  
  
- Vergewissern Sie sich, dass der Code, mit dem das <xref:System.Runtime.InteropServices.SafeHandle>-Objekt mit einem gültigen unformatierten Handlewert initialisiert wird, das Handle besitzt. Wenn Sie ein <xref:System.Runtime.InteropServices.SafeHandle>-Objekt um ein Handle herum erstellen, das sich nicht im Besitz des Codes befindet, und wenn Sie den `ownsHandle`-Parameter im Basiskonstruktor nicht auf `false` festlegen, können sowohl das <xref:System.Runtime.InteropServices.SafeHandle>-Objekt als auch der tatsächliche Handlebesitzer versuchen, das Handle zu schließen. Dies führt dann zu einem Fehler im <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A>-Objekt, wenn das <xref:System.Runtime.InteropServices.SafeHandle>-Objekt das Rennen verliert.  
  
- Wenn ein <xref:System.Runtime.InteropServices.SafeHandle>-Objekt zwischen Anwendungsdomänen gemarshallt wird, müssen Sie vergewissern, dass die verwendete <xref:System.Runtime.InteropServices.SafeHandle>-Ableitung als serialisierbar gekennzeichnet wurde. In den seltenen Fällen, in denen eine aus <xref:System.Runtime.InteropServices.SafeHandle> abgeleitete Klasse serialisierbar gemacht wurde, muss sie die <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle implementieren oder eines der anderen Verfahren zum manuellen Steuern der Serialisierung und Deserialisierung verwenden. Dies ist erforderlich, weil bei der standardmäßigen Serialisierungsaktion ein bitweiser Klon des eingeschlossenen unformatierten Handlewerts erstellt wird, was dazu führt, dass für zwei <xref:System.Runtime.InteropServices.SafeHandle>-Instanzen angenommen wird, dass sie dasselbe Handle besitzen. Beide Instanzen werden irgendwann versuchen, <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> für dasselbe Handle aufzurufen. Das zweite <xref:System.Runtime.InteropServices.SafeHandle>-Objekt, das dies versucht, schlägt dann fehl. Das richtige Vorgehen beim Serialisieren eines <xref:System.Runtime.InteropServices.SafeHandle>-Objekts besteht darin, für den systemeigenen Handletyp die `DuplicateHandle`-Funktion oder eine ähnliche Funktion aufzurufen, damit eine unabhängige gültige Handlekopie erstellt wird. Wenn Ihr Handletyp dies nicht unterstützt, kann der <xref:System.Runtime.InteropServices.SafeHandle>-Typ, der ihn umschließt, nicht serialisierbar gemacht werden.  
  
- Möglicherweise können Sie verfolgen, wo ein Handle vorzeitig geschlossen wird, wodurch sich ein Fehler ergibt, wenn schließlich die <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A>-Methode aufgerufen wird. Platzieren Sie dazu einen Debuggerhaltepunkt in dernativen Routine, in der das Handle freigegeben wird, also z. B. in der `CloseHandle`-Funktion. Dies ist möglicherweise für Belastungsszenarios oder sogar für mittelgroße Funktionstests wegen des umfangreichen Datenverkehrs nicht möglich, den solche Routinen oft verarbeiten müssen. Es kann nützlich sein, den Code zu instrumentieren, der die systemeigene Freigabemethode aufruft. So lässt sich die Identität des Aufrufers oder möglicherweise eine vollständige Stapelüberwachung sowie der Wert des Handles erfassen, das freigegeben wird.  Der Handlewert kann mit dem von diesem MDA gemeldeten Wert verglichen werden.  
  
- Beachten Sie, dass für einige systemeigene Handletypen, z. B. alle Win32-Handles, die über die `CloseHandle`-Funktion freigegeben werden können, derselbe Handlenamespace verwendet wird. Eine fehlerhafte Freigabe eines Handletyps kann zu Problemen mit einem anderen Handletyp führen. Wird beispielsweise ein Win32-Ereignishandle versehentlich zweimal geschlossen, kann die Folge sein, dass ein davon anscheinend unabhängiges Dateihandle vorzeitig geschlossen wird. Dies geschieht, wenn das Handle freigegeben und der Handlewert verfügbar wird, um eine andere Ressource zu verfolgen, die möglicherweise einen anderen Typ hat. Falls dies passiert und eine fehlerhafte zweite Freigabe erfolgt, wird möglicherweise das Handle eines unabhängigen Threads ungültig gemacht.  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die CLR.  
  
## <a name="output"></a>Output  
 Eine Meldung, die angibt, dass ein <xref:System.Runtime.InteropServices.SafeHandle> oder ein <xref:System.Runtime.InteropServices.CriticalHandle> das Handle nicht ordnungsgemäß freigegeben hat. Beispiel:  
  
```output
"A SafeHandle or CriticalHandle of type 'MyBrokenSafeHandle'
failed to properly release the handle with value 0x0000BEEF. This
usually indicates that the handle was released incorrectly via
another means (such as extracting the handle using DangerousGetHandle
and closing it directly or building another SafeHandle around it."  
```  
  
## <a name="configuration"></a>Konfiguration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <releaseHandleFailed/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>Beispiel  
 Das Folgende ist ein Codebeispiel, in dem der `releaseHandleFailed`-MDA aktiviert werden kann.  
  
```csharp
bool ReleaseHandle()  
{  
    // Calling the Win32 CloseHandle function to release the
    // native handle wrapped by this SafeHandle. This method returns
    // false on failure, but should only fail if the input is invalid
    // (which should not happen here). The method specifically must not
    // fail simply because of lack of resources or other transient
    // failures beyond the user’s control. That would make it unacceptable
    // to call CloseHandle as part of the implementation of this method.  
    return CloseHandle(handle);  
}  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](diagnosing-errors-with-managed-debugging-assistants.md)
- [Interop Marshaling (Interop-Marshalling)](../interop/interop-marshaling.md)
