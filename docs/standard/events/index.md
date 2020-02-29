---
title: Behandeln und Auslösen von Ereignissen
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- delegate model for events
- application development [.NET], events
- application development [.NET Framework], events
- application development [.NET Core], events
- events [.NET]
- events [.NET Core]
- events [.NET Framework]
ms.assetid: b6f65241-e0ad-4590-a99f-200ce741bb1f
ms.openlocfilehash: b8ed028bc1edabf14d7b2dd67d94b28d574d2eb4
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159623"
---
# <a name="handling-and-raising-events"></a>Behandeln und Auslösen von Ereignissen

Ereignisse in .NET basieren auf dem Delegatmodell. Das Delegatmodell folgt dem [Beobachterentwurfsmuster](observer-design-pattern.md), mit dem sich ein Abonnent bei einem Anbieter registrieren und Benachrichtigungen von diesem empfangen kann. Von einem Ereignissender wird eine Benachrichtigung erstellt, die angibt, dass ein Ereignis aufgetreten ist. Diese Benachrichtigung wird dann vom Ereignisempfänger empfangen, und eine Antwort wird definiert. In diesem Artikel werden die Hauptkomponenten des Delegatmodells, das Verwenden von Ereignissen in Anwendungen und das Implementieren von Ereignissen im Code beschrieben.  
  
 Informationen zur Ereignisbehandlung bei Windows 8.x Store-Apps finden Sie unter [Events and routed events overview (Übersicht über Ereignisse und Routingereignisse)](https://docs.microsoft.com/previous-versions/windows/apps/hh758286(v=win.10)).  
  
## <a name="events"></a>Ereignisse

Ein Ereignis ist eine Meldung, die von einem Objekt gesendet wird, um das Auftreten einer Aktion zu signalisieren. Die Aktion kann durch Benutzerinteraktionen wie das Klicken auf eine Schaltfläche verursacht werden, oder sie kann durch eine andere Programmlogik, z.B. das Ändern eines Eigenschaftswerts, ausgelöst werden. Das Objekt, von dem das Ereignis ausgelöst wird, wird als *Ereignissender* bezeichnet. Dem Ereignissender ist nicht bekannt, welches Objekt oder welche Methode die ausgelösten Ereignisse empfangen (behandeln) wird. Das Ereignis ist in der Regel ein Member des Ereignissenders. Beispielsweise ist das <xref:System.Web.UI.WebControls.Button.Click>-Ereignis ein Member der Klasse <xref:System.Web.UI.WebControls.Button>, und das <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged>-Ereignis ist ein Member der Klasse, von der die <xref:System.ComponentModel.INotifyPropertyChanged>-Schnittstelle implementiert wird.  
  
Zum Definieren eines Ereignisses verwenden Sie entweder das Schlüsselwort [`event`](../../csharp/language-reference/keywords/event.md) (in C#) oder das Schlüsselwort [`Event`](../../visual-basic/language-reference/statements/event-statement.md) (in Visual Basic) in der Signatur der Ereignisklasse und geben den Typ des Delegaten für das Ereignis an. Delegaten werden im nächsten Abschnitt erläutert.  
  
In der Regel fügen Sie zum Auslösen eines Ereignisses eine Methode hinzu, die als `protected` und `virtual` (in C#) bzw. `Protected` und `Overridable` (in Visual Basic) gekennzeichnet ist. Nennen Sie diese Methode `On`*EventName* (zum Beispiel `OnDataReceived`). Von dieser Methode muss ein Parameter akzeptiert werden, der ein Ereignisdatenobjekt angibt, welches ein Objekt des Typs <xref:System.EventArgs> oder eines abgeleiteten Typs ist. Sie stellen diese Methode bereit, damit abgeleitete Klassen die Logik zum Auslösen des Ereignisses überschreiben können. Eine abgeleitete Klasse sollte immer die `On`*EventName*-Methode der Basisklasse aufrufen, um sicherzustellen, dass registrierte Delegaten das Ereignis empfangen.  

Im folgenden Beispiel wird die Deklaration eines Ereignisses namens `ThresholdReached`erläutert. Das Ereignis wird dem <xref:System.EventHandler>-Delegaten zugeordnet, und es wird in einer Methode namens `OnThresholdReached` ausgelöst.  
  
 [!code-csharp[EventsOverview#1](~/samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programtruncated.cs#1)]
 [!code-vb[EventsOverview#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1truncated.vb#1)]  
  
## <a name="delegates"></a>Delegaten

Ein Delegat ist ein Typ, der einen Verweis auf eine Methode enthält. Ein Delegat wird mit einer Signatur deklariert, die den Rückgabetyp und die Parameter für die Methoden angibt, auf die er verweist. Er kann nur Verweise auf Methoden enthalten, die mit der Signatur übereinstimmen. Ein Delegat entspricht insofern einem typsicheren Funktionszeiger oder einem Rückruf. Mit einer Delegatdeklaration ist eine Delegatklasse ausreichend definiert.  
  
Delegaten können in .NET vielfältig verwendet werden. Im Kontext der Ereignisse ist ein Delegat ein Mittler (oder ein zeigerähnlicher Mechanismus) zwischen der Ereignisquelle und dem Code, mit dem das Ereignis behandelt wird. Sie weisen einen Delegaten einem Ereignis zu, indem Sie den Delegattyp in der Ereignisdeklaration, wie im Beispiel des vorherigen Abschnitts veranschaulicht, einschließen. Weitere Informationen zu Delegaten finden Sie unter der <xref:System.Delegate>-Klasse.  
  
.NET stellt die Delegaten <xref:System.EventHandler> und <xref:System.EventHandler%601> zur Unterstützung der meisten Ereignisszenarien bereit. Verwenden Sie den <xref:System.EventHandler>-Delegaten für alle Ereignisse, in denen keine Ereignisdaten enthalten sind. Verwenden Sie den <xref:System.EventHandler%601>-Delegaten für Ereignisse, die Daten über das Ereignis enthalten. Diese Delegaten verfügen über keinen Rückgabetypwert und akzeptieren zwei Parameter (ein Objekt für die Ereignisquelle sowie ein Objekt für Ereignisdaten).  
  
Delegaten sind [Multicastdelegaten](xref:System.MulticastDelegate), d.h., sie können Verweise auf mehrere Methoden für die Ereignisbehandlung enthalten. Weitere Informationen finden Sie auf der <xref:System.Delegate>-Referenzseite. Delegaten bieten Flexibilität und eine genaue Steuerung bei der Ereignisbehandlung. Ein Delegat fungiert als ein Ereignisverteiler für die Klasse, die das Ereignis auslöst, indem er eine Liste der registrierten Ereignishandler für das Ereignis verwaltet.  
  
Für Szenarien, in denen die Delegaten <xref:System.EventHandler> und <xref:System.EventHandler%601> nicht funktionieren, können Sie einen Delegaten definieren. Szenarien, für die Sie einen Delegaten definieren müssen, sind sehr selten, z. B. bei der Arbeit mit Code, von dem keine Generics erkannt werden. Markieren Sie einen Delegaten mit dem Schlüsselwort [`delegate`](../../csharp/language-reference/builtin-types/reference-types.md#the-delegate-type) (in C#) und dem Schlüsselwort [`Delegate`](../../visual-basic/language-reference/statements/delegate-statement.md) (in Visual Basic) in der Deklaration. Im folgenden Beispiel wird die Deklaration eines Delegaten namens `ThresholdReachedEventHandler` erläutert.  
  
[!code-csharp[EventsOverview#4](~/samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programtruncated.cs#4)]
[!code-vb[EventsOverview#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1truncated.vb#4)]  
  
## <a name="event-data"></a>Ereignisdaten

Daten, die einem Ereignis zugewiesen sind, können durch eine Ereignisdatenklasse bereitgestellt werden. In .NET werden viele Ereignisdatenklassen für die Verwendung in Ihren Anwendungen bereitgestellt. Zum Beispiel ist die <xref:System.IO.Ports.SerialDataReceivedEventArgs>-Klasse die Ereignisdatenklasse für das <xref:System.IO.Ports.SerialPort.DataReceived?displayProperty=nameWithType>-Ereignis. .NET folgt einem Benennungsmuster, bei dem alle Ereignisdatenklassen auf `EventArgs` enden. Sie bestimmen, welche Ereignisdatenklasse einem Ereignis zugeordnet wird, indem Sie den Delegaten nach dem Ereignis durchsuchen. Zum Beispiel enthält der <xref:System.IO.Ports.SerialDataReceivedEventHandler>-Delegat die <xref:System.IO.Ports.SerialDataReceivedEventArgs>-Klasse als einen seiner Parameter.  
  
Die <xref:System.EventArgs>-Klasse ist der Basistyp aller Ereignisdatenklassen. <xref:System.EventArgs> ist auch die Klasse, die bei einem Ereignis verwendet wird, dem keine Daten zugeordnet sind. Wenn Sie ein Ereignis erstellen, nur um andere Klassen über ein Geschehnis zu benachrichtigen, ohne dass Daten übergeben werden, schließen Sie die <xref:System.EventArgs>-Klasse als zweiten Parameter im Delegaten ein. Sie können den <xref:System.EventArgs.Empty?displayProperty=nameWithType>-Wert übergeben, wenn keine Daten bereitgestellt werden. Im <xref:System.EventHandler>-Delegat ist die <xref:System.EventArgs>-Klasse als Parameter enthalten.  
  
Wenn Sie eine benutzerdefinierte Ereignisdatenklasse erstellen möchten, erstellen Sie eine von <xref:System.EventArgs> abgeleitete Klasse, und stellen Sie dann alle Member bereit, die zum Übergeben der mit dem Ereignis verknüpften Daten erforderlich sind. In der Regel sollten Sie dem Benennungsmuster von .NET folgen und den Ereignisdaten-Klassennamen auf `EventArgs` enden lassen.  
  
Im folgenden Beispiel wird eine Ereignisdatenklasse `ThresholdReachedEventArgs` veranschaulicht. Darin sind Eigenschaften enthalten, die für das ausgelöste Ereignis spezifisch sind.  
  
[!code-csharp[EventsOverview#3](~/samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programtruncated.cs#3)]
[!code-vb[EventsOverview#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1truncated.vb#3)]  
  
## <a name="event-handlers"></a>Ereignishandler

Um auf ein Ereignis zu reagieren, definieren Sie eine Ereignishandlermethode im Ereignisempfänger. Diese Methode muss der Signatur des Delegaten für das von Ihnen behandelte Ereignis entsprechen. Im Ereignishandler führen Sie die Aktionen aus, die beim Auslösen des Ereignisses erforderlich sind, zum Beispiel das Sammeln von Benutzereingaben, nachdem der Benutzer auf eine Schaltfläche geklickt hat. Um bei Auftreten des Ereignisses Benachrichtigungen zu empfangen, muss die Ereignishandlermethode das Ereignis abonnieren.  
  
Im folgenden Beispiel wird die Ereignishandlermethode `c_ThresholdReached` dargestellt, die der Signatur für den <xref:System.EventHandler>-Delegaten entspricht. Die Methode abonniert das `ThresholdReached`-Ereignis.  
  
[!code-csharp[EventsOverview#2](~/samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programtruncated.cs#2)]
[!code-vb[EventsOverview#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1truncated.vb#2)]  
  
## <a name="static-and-dynamic-event-handlers"></a>Statische und dynamische Ereignishandler  

Mit .NET können sich Abonnenten entweder statisch oder dynamisch für Ereignisbenachrichtigungen registrieren. Statische Ereignishandler sind für die gesamte Lebensdauer der Klasse gültig, deren Ereignisse sie behandeln. Dynamische Ereignishandler werden bei der Programmausführung explizit aktiviert und deaktiviert. Dies erfolgt in der Regel als Reaktion auf eine bedingte Programmlogik. So können sie beispielsweise verwendet werden, wenn Ereignisbenachrichtigungen nur unter bestimmten Bedingungen erforderlich sind, oder wenn eine Anwendung mehrere Ereignishandler bereitstellt und über die Laufzeitbedingungen definiert wird, welcher davon verwendet wird. Im Beispiel des vorherigen Abschnitts wird das dynamische Hinzufügen eines Ereignishandlers veranschaulicht. Weitere Informationen finden Sie unter [Ereignisse (Visual Basic)](../../visual-basic/programming-guide/language-features/events/index.md) und [Ereignisse (C#-Programmierhandbuch)](../../csharp/programming-guide/events/index.md).  
  
## <a name="raising-multiple-events"></a>Auslösen mehrerer Ereignisse  
 Wenn von der Klasse mehrere Ereignisse ausgelöst werden, generiert der Compiler ein Feld pro Ereignisdelegatinstanz. Ist die Anzahl der Ereignisse sehr hoch, wird u. U. zu viel Speicher beansprucht, wenn für jeden Delegaten ein Feld generiert wird. Für solche Situationen werden in .NET Ereigniseigenschaften bereitgestellt, die Sie mit einer weiteren beliebig wählbaren Datenstruktur zum Speichern von Ereignisdelegaten verwenden können.  
  
 Ereigniseigenschaften bestehen aus Ereignisdeklarationen, die von Ereignisaccessoren begleitet werden. Ereignisaccessoren sind die von Ihnen definierten Methoden, mit denen Ereignisdelegatinstanzen der Speicherdatenstruktur hinzugefügt oder daraus entfernt werden können. Beachten Sie, dass Ereigniseigenschaften langsamer als Ereignisfelder sind, da jeder Ereignisdelegat abgerufen werden muss, bevor er aufgerufen werden kann. Sie müssen daher einen Kompromiss zwischen hoher Speicherauslastung und verminderter Geschwindigkeit finden. Wenn die Klasse viele Ereignisse definiert, die selten ausgelöst werden, können Sie Ereigniseigenschaften implementieren. Weitere Informationen finden Sie unter [Vorgehensweise: Behandeln mehrerer Ereignisse mit Ereigniseigenschaften](how-to-handle-multiple-events-using-event-properties.md).  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[How to: Auslösen und Behandeln von Ereignissen](how-to-raise-and-consume-events.md)|In diesem Abschnitt sind Beispiele zum Auslösen und Verarbeiten von Ereignissen enthalten.|  
|[How to: Behandeln mehrerer Ereignisse mit Ereigniseigenschaften](how-to-handle-multiple-events-using-event-properties.md)|In diesem Abschnitt wird die Verwendung von Ereigniseigenschaften zum Behandeln mehrerer Ereignisse veranschaulicht.|  
|[Beobachterentwurfsmuster](observer-design-pattern.md)|Das Entwurfsmuster, mit dem sich ein Abonnent bei einem Anbieter registrieren und Benachrichtigungen von diesem empfangen kann, wird beschrieben.|  
|[How to: Verarbeiten von Ereignissen in einer Web Forms-Anwendung](how-to-consume-events-in-a-web-forms-application.md)|In diesem Abschnitt wird das Behandeln eines Ereignisses, das von einem Web Forms-Steuerelement ausgelöst wird, veranschaulicht.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.EventHandler>
- <xref:System.EventHandler%601>
- <xref:System.EventArgs>
- <xref:System.Delegate>
- [Ereignisse (Visual Basic)](../../visual-basic/programming-guide/language-features/events/index.md)
- [Ereignisse (C#-Programmierhandbuch)](../../csharp/programming-guide/events/index.md)
- [Übersicht über Ereignisse und Routingereignisse (UWP-Apps)](/windows/uwp/xaml-platform/events-and-routed-events-overview)
