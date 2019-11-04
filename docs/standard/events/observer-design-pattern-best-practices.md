---
title: Empfohlene Vorgehensweisen für Beobachterentwurfsmuster
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- observer design pattern [.NET Framework], best practices
- best practices [.NET Framework], observer design pattern
ms.assetid: c834760f-ddd4-417f-abb7-a059679d5b8c
ms.openlocfilehash: 2da29e0baf429142707d0ddd39b1a11c13a17a90
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141538"
---
# <a name="observer-design-pattern-best-practices"></a>Empfohlene Vorgehensweisen für Beobachterentwurfsmuster
Im .NET Framework wird das Beobachterentwurfsmuster als Satz von Schnittstellen implementiert. Die <xref:System.IObservable%601?displayProperty=nameWithType>-Schnittstelle stellt den Datenanbieter dar, der auch für die Bereitstellung einer <xref:System.IDisposable>-Implementierung verantwortlich ist, mit der Beobachter Benachrichtigungsabonnements kündigen können. Die <xref:System.IObserver%601?displayProperty=nameWithType>-Schnittstelle stellt den Beobachter dar. Dieses Thema beschreibt die empfohlenen Vorgehensweisen, die Entwickler befolgen sollten, wenn sie das Beobachterentwurfsmuster unter Verwendung dieser Schnittstellen implementieren.  
  
## <a name="threading"></a>Threading  
 In der Regel implementiert ein Anbieter die <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType>-Methode, indem er einen bestimmten Beobachter einer Abonnentenliste hinzufügt, die durch ein Auflistungsobjekt dargestellt wird, und implementiert die <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>-Methode, indem ein bestimmten Beobachter aus der Abonnentenliste entfernt wird. Ein Beobachter kann diese Methoden jederzeit aufrufen. Da der Anbieter/Beobachter-Vertrag außerdem nicht angibt, wer für das Kündigen nach der <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>-Callbackmethode verantwortlich ist, können der Anbieter und der Beobachter beide versuchen, denselben Member aus der Liste zu entfernen. Aufgrund dieser Möglichkeit sollten die <xref:System.IObservable%601.Subscribe%2A>- und die <xref:System.IDisposable.Dispose%2A>-Methode threadsicher sein. In der Regel umfasst dies die Verwendung einer [gleichzeitigen Auflistung](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md) oder eine Sperre. Für Implementierungen, die nicht threadsicher sind, sollte dies explizit dokumentiert werden.  
  
 Alle weiteren Garantien müssen in einer Ebene über dem Anbieter/Beobachter-Vertrag angegeben werden. Implementierer sollten klar kommunizieren, wenn sie zusätzliche Anforderungen auferlegen, um Verwirrungen der Benutzer zum Beobachtervertrag zu vermeiden.  
  
## <a name="handling-exceptions"></a>Behandeln von Ausnahmen  
 Aufgrund der losen Kopplung zwischen einem Datenanbieter und einem Beobachter sollen Ausnahmen im Beobachterentwurfsmuster nur der Information dienen. Dies beeinflusst das Verarbeiten von Ausnahmen im Beobachterentwurfsmuster durch Anbieter und Beobachter.  
  
### <a name="the-provider----calling-the-onerror-method"></a>Der Anbieter – Aufrufen der OnError-Methode  
 Die <xref:System.IObserver%601.OnError%2A>-Methode dient als Informationsmeldung an Beobachter – ähnlich wie die <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>-Methode. Allerdings wurde die <xref:System.IObserver%601.OnNext%2A>-Methode entwickelt, um einem Beobachter aktuelle bzw. aktualisierte Daten bereitzustellen, während die <xref:System.IObserver%601.OnError%2A>-Methode entwickelt wurde, um anzugeben, dass der Anbieter keine gültige Daten bereitstellen kann.  
  
 Der Anbieter sollte diese empfohlenen Vorgehensweisen beim Verarbeiten von Ausnahmen und dem Aufrufen der <xref:System.IObserver%601.OnError%2A>-Methode verwenden:  
  
- Der Anbieter muss seine eigenen Ausnahmen verarbeiten, wenn er spezielle Anforderungen hat.  
  
- Der Anbieter sollte nicht erwarten oder voraussetzen, dass Beobachter Ausnahmen auf eine bestimmte Weise verarbeiten.  
  
- Der Anbieter sollte die <xref:System.IObserver%601.OnError%2A>-Methode aufrufen, wenn er eine Ausnahme behandelt, die die Bereitstellung von Updates gefährdet. Informationen zu solchen Ausnahmen können an den Beobachter übergeben werden. In anderen Fällen besteht keine Notwendigkeit, den Beobachter über eine Ausnahme zu benachrichtigen.  
  
 Sobald der Anbieter die <xref:System.IObserver%601.OnError%2A>- oder <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>-Methode aufruft, sollte es keine weiteren Benachrichtigungen geben, und der Anbieter kann seine Beobachter kündigen. Allerdings können die Beobachter das Abonnement auch jederzeit selbst kündigen, auch bevor oder nachdem sie eine <xref:System.IObserver%601.OnError%2A>- oder <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>-Benachrichtigung empfangen. Das Beobachterentwurfsmuster schreibt nicht vor, ob der Anbieter oder der Beobachter für die Kündigung zuständig ist; aus diesem Grund besteht die Möglichkeit, dass beide versuchen, zu kündigen. Wenn Beobachter kündigen, werden sie in der Regel aus einer Abonnentenauflistung entfernt. In einer Single-Thread-Anwendung sollte die <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>-Implementierung sicherstellen, dass ein Objektverweis gültig ist und dass das Objekt ein Mitglied der Abonnentenauflistung ist, bevor der Versuch unternommen wird, es zu entfernen. In einer Multithreadanwendung sollte ein threadsicheres Auflistungsobjekt, z. B. ein <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType>-Objekt, verwendet werden.  
  
### <a name="the-observer----implementing-the-onerror-method"></a>Der Beobachter – Implementieren der OnError-Methode  
 Wenn ein Beobachter eine Fehlerbenachrichtigung von einem Anbieter empfängt, sollte der Beobachter die Ausnahme als Informationsmeldung behandeln und sollte nicht verpflichtet sein, bestimmte Maßnahmen zu ergreifen.  
  
 Der Beobachter sollte diesen empfohlenen Vorgehensweisen bei der Reaktion auf einen <xref:System.IObserver%601.OnError%2A>-Methodenaufruf von einem Anbieter folgen:  
  
- Der Beobachter sollte keine Ausnahmen in seinen Schnittstellenimplementierungen auslösen, z. B. <xref:System.IObserver%601.OnNext%2A> oder <xref:System.IObserver%601.OnError%2A>. Wenn der Beobachter aber Ausnahmen auslöst, sollte er davon ausgehen, dass diese Ausnahmen nicht behandelt werden.  
  
- Um die Aufrufliste beizubehalten, sollte ein Beobachter, der ein <xref:System.Exception>-Objekt, das an die <xref:System.IObserver%601.OnError%2A>-Methode übergeben wurde, auslösen möchte, die Ausnahme vor dem Auslösen umschließen. Zu diesem Zweck sollte ein Standardausnahmeobjekt verwendet werden.  
  
## <a name="additional-best-practices"></a>Weitere empfohlene Vorgehensweisen  
 Der Versuch, die Registrierung in der <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType>-Methode aufzuheben, kann in einem Nullverweis resultieren. Aus diesem Grund wird empfohlen, dieses Verfahren zu vermeiden.  
  
 Es ist zwar möglich, einen Beobachter an mehrere Anbieter anzufügen, das empfohlene Muster ist aber das Anfügen einer <xref:System.IObserver%601>-Instanz an nur eine <xref:System.IObservable%601>-Instanz.  
  
## <a name="see-also"></a>Siehe auch

- [Beobachterentwurfsmuster](../../../docs/standard/events/observer-design-pattern.md)
- [Vorgehensweise: Implementieren eines Observers](../../../docs/standard/events/how-to-implement-an-observer.md)
- [Vorgehensweise: Implementieren eines Anbieters](../../../docs/standard/events/how-to-implement-a-provider.md)
