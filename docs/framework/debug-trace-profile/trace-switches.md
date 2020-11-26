---
title: Ablaufverfolgungsschalter
description: Untersuchen Sie die Ablauf Verfolgungs Schalter, mit denen Sie die Ablauf Verfolgungs Ausgabe aktivieren, deaktivieren und Filtern können. .NET stellt die Klassen BooleanSwitch, TraceSwitch und SourceSwitch bereit.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tracing [.NET Framework], trace switches
- trace switches, about trace switches
- tracing [.NET Framework], level of detail
- switches, trace
- trace switches
- trace switches, creating custom
ms.assetid: 8ab913aa-f400-4406-9436-f45bc6e54fbe
ms.openlocfilehash: dfbff0a78b3c6c1318224ccc9608c1b816f9d5f1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238053"
---
# <a name="trace-switches"></a>Ablaufverfolgungsschalter

Mit Ablaufverfolgungsschaltern können Sie die Ablaufverfolgungsausgabe aktivieren, deaktivieren und filtern. Diese Schalter sind Objekte, die im Code vorhanden sind und extern über die Konfigurationsdatei (CONFIG) konfiguriert werden können. .NET Framework bietet drei Typen von Ablaufverfolgungsschaltern: die <xref:System.Diagnostics.BooleanSwitch> -Klasse, die <xref:System.Diagnostics.TraceSwitch> -Klasse und die <xref:System.Diagnostics.SourceSwitch> -Klasse. Die <xref:System.Diagnostics.BooleanSwitch> -Klasse fungiert als Umschalter, d. h., sie aktiviert oder deaktiviert eine Vielzahl von Ablaufverfolgungsanweisungen. Mit der <xref:System.Diagnostics.TraceSwitch> -Klasse und der <xref:System.Diagnostics.SourceSwitch> -Klasse können Sie einen Ablaufverfolgungsschalter für eine bestimmte Ablaufverfolgungsebene aktivieren, sodass die für diese und alle darunter liegenden Ebenen angegebenen <xref:System.Diagnostics.Trace> - oder <xref:System.Diagnostics.TraceSource> -Meldungen angezeigt werden. Wenn Sie den Schalter deaktivieren, werden die Ablaufverfolgungsmeldungen nicht angezeigt. All diese Klassen werden von der abstrakten (**MustInherit**) **Switch**-Klasse abgeleitet. Dies gilt für alle von Benutzern entwickelten Schalter.  
  
 Ablaufverfolgungsschalter können beim Filtern von Informationen hilfreich sein. Beispiel: In einem Datenzugriffsmodul sollen alle Ablaufverfolgungsmeldungen, in der restlichen Anwendung aber nur Fehlermeldungen angezeigt werden. In diesem Fall verwenden Sie einen Ablaufverfolgungsschalter für das Datenzugriffsmodul und einen Schalter für die restliche Anwendung. Wenn Sie die Schalter in der CONFIG-Datei mit den entsprechenden Einstellungen konfigurieren, können Sie steuern, welche Typen von Ablaufverfolgungsmeldungen Sie empfangen. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen, Initialisieren und Konfigurieren von Ablaufverfolgungsschaltern](how-to-create-initialize-and-configure-trace-switches.md).  
  
 Eine bereitgestellte Anwendung wird in der Regel mit deaktivierten Schaltern ausgeführt, damit die Benutzer nicht auf viele irrelevante Ablaufverfolgungsmeldungen achten müssen, die beim Ausführen der Anwendung auf dem Bildschirm angezeigt oder in einer Protokolldatei abgelegt werden. Wenn bei der Anwendungsausführung ein Problem auftritt, können Sie die Anwendung beenden, die Schalter aktivieren und die Anwendung neu starten. Dann werden die Ablaufverfolgungsmeldungen angezeigt.  
  
 Damit Sie einen Schalter verwenden können, müssen Sie zunächst ein Schalterobjekt in einer **BooleanSwitch** -Klasse, einer **TraceSwitch** -Klasse oder einer entwicklerdefinierten Klasse erstellen. Weitere Informationen zum Erstellen entwicklerdefinierter Schalter finden Sie unter <xref:System.Diagnostics.Switch> -Klasse in der Referenz zu .NET Framework. Anschließend legen Sie einen Konfigurationswert fest, der angibt, wann das Schalterobjekt verwendet werden soll. Dann testen Sie die Einstellung des Schalterobjekts in verschiedenen **Trace** -Ablaufverfolgungsmethoden (oder **Debug**-Ablaufverfolgungsmethoden).  
  
## <a name="trace-levels"></a>Ablaufverfolgungsebenen  

 Bei Verwendung von **TraceSwitch** sind noch weitere Aspekte zu beachten. Ein **TraceSwitch** -Objekt hat vier Eigenschaften, die Werte vom Typ **Boolean** zurückgeben und angeben, ob der Schalter für mindestens eine bestimmte Ebene festgelegt ist:  
  
- <xref:System.Diagnostics.TraceSwitch.TraceError%2A?displayProperty=nameWithType>  
  
- <xref:System.Diagnostics.TraceSwitch.TraceWarning%2A?displayProperty=nameWithType>  
  
- <xref:System.Diagnostics.TraceSwitch.TraceInfo%2A?displayProperty=nameWithType>  
  
- <xref:System.Diagnostics.TraceSwitch.TraceVerbose%2A?displayProperty=nameWithType>  
  
 Mit Ebenen können Sie die Menge der empfangenen Ablaufverfolgungsinformationen auf die zur Lösung eines Problems benötigten Informationen einschränken. Sie geben die gewünschte Detailstufe für die Ablaufverfolgungsausgabe an, indem Sie Ablaufverfolgungsschalter für die entsprechende Ablaufverfolgungsebene festlegen und konfigurieren. Sie können Fehlermeldungen, Warnmeldungen, Informationsmeldungen, ausführliche Ablaufverfolgungsmeldungen oder gar keine Meldungen erhalten.  
  
 Welchen Meldungstyp Sie den einzelnen Ebenen zuordnen, bleibt Ihnen überlassen. In der Regel richtet sich der Inhalt der Ablaufverfolgungsmeldungen nach den jeweiligen Ebenenzuordnungen, Sie bestimmen jedoch die Unterschiede zwischen den Ebenen. Sie könnten beispielsweise auf Ebene 3 (**Info**) detaillierte Problembeschreibungen und auf Ebene 1 (**Error**) nur Fehlerverweisnummern zur Verfügung stellen. Welches Schema für Ihre Anwendung am besten geeignet ist, entscheiden Sie.  
  
 Diese Eigenschaften entsprechen den Werten 1 bis 4 der **TraceLevel** -Enumeration. In der folgenden Tabelle werden die Ebenen der **TraceLevel** -Enumeration und ihre Werte aufgeführt.  
  
|Enumerationswert|Ganzzahliger Wert|Angezeigter (oder in angegebenes Ausgabeziel geschriebener) Meldungstyp|  
|----------------------|-------------------|---------------------------------------------------------------------------|  
|Aus|0|Keine|  
|Fehler|1|Nur Fehlermeldungen|  
|Warnung|2|Warnmeldungen und Fehlermeldungen|  
|Info|3|Informationsmeldungen, Warnmeldungen und Fehlermeldungen|  
|Ausführlich|4|Ausführliche Meldungen, Informationsmeldungen, Warnmeldungen und Fehlermeldungen|  
  
 Die **TraceSwitch** -Eigenschaften geben die oberste Ablaufverfolgungsebene für den Schalter an. Das bedeutet, dass Ablaufverfolgungsinformationen sowohl für die angegebene Ebene als auch für alle niedrigeren Ebenen geschrieben werden. Wenn **TraceInfo** z. B. **true** ist, sind **TraceError** und **TraceWarning** ebenfalls **true** . **TraceVerbose** kann jedoch **false** sein.  
  
 Diese Eigenschaften sind schreibgeschützt. Sie werden beim Festlegen der **TraceLevel** -Eigenschaft automatisch durch das **TraceSwitch** -Objekt festgelegt. Beispiel:  
  
```vb  
Dim myTraceSwitch As New TraceSwitch("SwitchOne", "The first switch")  
myTraceSwitch.Level = TraceLevel.Info  
' This message box displays true, because setting the level to  
' TraceLevel.Info sets all lower levels to true as well.  
MessageBox.Show(myTraceSwitch.TraceWarning.ToString())  
' This messagebox displays false.  
MessageBox.Show(myTraceSwitch.TraceVerbose.ToString())  
```  
  
```csharp  
System.Diagnostics.TraceSwitch myTraceSwitch =
   new System.Diagnostics.TraceSwitch("SwitchOne", "The first switch");  
myTraceSwitch.Level = System.Diagnostics.TraceLevel.Info;  
// This message box displays true, because setting the level to
// TraceLevel.Info sets all lower levels to true as well.  
MessageBox.Show(myTraceSwitch.TraceWarning.ToString());  
// This message box displays false.  
MessageBox.Show(myTraceSwitch.TraceVerbose.ToString());  
```  
  
## <a name="developer-defined-switches"></a>Entwicklerdefinierte Schalter  

 Zusätzlich zur Bereitstellung von **BooleanSwitch** und **TraceSwitch** können Sie auch eigene Schalter definieren, indem Sie die Einstellungen von der **Switch** -Klasse erben und die Basisklassenmethoden mit benutzerdefinierten Methoden überschreiben. Weitere Informationen zum Erstellen entwicklerdefinierter Schalter finden Sie unter <xref:System.Diagnostics.Switch> -Klasse in der Referenz zu .NET Framework.  
  
## <a name="see-also"></a>Weitere Informationen

- [Ablaufverfolgungslistener](trace-listeners.md)
- [Vorgehensweise: Hinzufügen von Ablaufverfolgungsanweisungen zu Anwendungscode](how-to-add-trace-statements-to-application-code.md)
- [Ablaufverfolgung und Instrumentieren von Anwendungen](tracing-and-instrumenting-applications.md)
