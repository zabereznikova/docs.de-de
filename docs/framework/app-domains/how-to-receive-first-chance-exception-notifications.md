---
title: 'Vorgehensweise: Empfangen von Ausnahmebenachrichtigungen (erste Chance)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- first-chance exception notifications
- exceptions, first chance notifications
ms.assetid: 66f002b8-a97d-4a6e-a503-2cec01689113
ms.openlocfilehash: da60dfca424f7c10e810b5e083ff7fa63a688218
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119865"
---
# <a name="how-to-receive-first-chance-exception-notifications"></a>Vorgehensweise: Empfangen von Ausnahmebenachrichtigungen (erste Chance)
Mit dem <xref:System.AppDomain.FirstChanceException>-Ereignis der <xref:System.AppDomain>-Klasse erhalten Sie eine Benachrichtigung bezüglich einer ausgelösten Ausnahme, bevor die CLR mit der Suche nach Ausnahmehandlern beginnt.

 Das Ereignis wird auf Ebene der Anwendungsdomäne ausgelöst. Ein Ausführungsthread kann verschiedene Anwendungsdomänen durchlaufen. Es ist also möglich, dass ein Ausnahmefehler aus einer Anwendungsdomäne in einer anderen behandelt wird. Die Benachrichtigung findet in jeder Anwendungsdomäne statt, die einen Handler für das Ereignis hinzugefügt hat, bis eine Anwendungsdomäne die Ausnahme behandelt.

 Die Verfahren und Beispiele in diesem Artikel zeigen, wie Sie Benachrichtigungen über Ausnahmefehler der ersten Chance in einem einfachen Programm mit einer Anwendungsdomäne und in einer von Ihnen selbst erstellten Anwendungsdomäne erhalten.

 Ein umfangreicheres Beispiel, das mehrere Anwendungsdomänen umfasst, finden Sie im Beispiel zum <xref:System.AppDomain.FirstChanceException>-Ereignis.

## <a name="receiving-first-chance-exception-notifications-in-the-default-application-domain"></a>Empfangen von Benachrichtigungen über Ausnahmefehler der ersten Chance in Standardanwendungsdomänen
 In der folgenden Prozedur, dem Einstiegspunkt der Anwendung (`Main()`-Methode), wird in der Standardanwendungsdomäne ausgeführt.

#### <a name="to-demonstrate-first-chance-exception-notifications-in-the-default-application-domain"></a>So demonstrieren Sie Benachrichtigungen über Ausnahmefehler der ersten Chance in der Standardanwendungsdomäne

1. Definieren Sie mithilfe einer Lambda-Funktion einen Ereignishandler für das <xref:System.AppDomain.FirstChanceException>-Ereignis, und fügen Sie ihn an das Ereignis an. In diesem Beispiel gibt der Ereignishandler den Namen der Anwendungsdomäne, in der das Ereignis behandelt wurde, und die <xref:System.Exception.Message%2A>-Eigenschaft der Ausnahme aus.

     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#2)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#2)]

2. Lösen Sie eine Ausnahme aus, und fangen Sie sie ab. Bevor die Runtime den Ausnahmehandler sucht, wird das <xref:System.AppDomain.FirstChanceException>-Ereignis ausgelöst und eine Meldung angezeigt. Auf diese Nachricht folgt die Nachricht, die vom Ausnahmehandler angezeigt wird.

     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#3)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#3)]

3. Lösen Sie eine Ausnahme aus, aber fangen Sie sie nicht ab. Bevor die Runtime nach einem Ausnahmehandler sucht, wird das <xref:System.AppDomain.FirstChanceException>-Ereignis ausgelöst und eine Meldung angezeigt. Da es keinen Ausnahmehandler gibt, wird die Anwendung beendet.

     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#4)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#4)]

     Der Code aus den ersten drei Schritten dieser Prozedur stellt eine vollständige Konsolenanwendung dar. Die Ausgabe der Anwendung variiert je nach dem Namen der ausführbaren Datei, denn der Name der Standardanwendungsdomäne besteht aus dem Namen und der Erweiterung der ausführbaren Datei. Ein Beispiel finden Sie in der folgenden Ausgabe.

     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#5)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#5)]

## <a name="receiving-first-chance-exception-notifications-in-another-application-domain"></a>Empfangen von Benachrichtigungen über Ausnahmefehler der ersten Chance in einer anderen Anwendungsdomäne
 Wenn Ihr Programm mehr als eine Anwendungsdomäne enthält, können Sie auswählen, welche Anwendungsdomänen Benachrichtigungen erhalten.

#### <a name="to-receive-first-chance-exception-notifications-in-an-application-domain-that-you-create"></a>So empfangen Sie Benachrichtigungen über Ausnahmefehler der ersten Chance in einer selbst erstellten Anwendungsdomäne

1. Definieren Sie einen Ereignishandler für das <xref:System.AppDomain.FirstChanceException>-Ereignis. In diesem Beispiel wird eine `static`-Methode verwendet (`Shared`-Methode in Visual Basic), die den Namen der Anwendungsdomäne, in der das Ereignis behandelt wurde, und die <xref:System.Exception.Message%2A>-Eigenschaft der Ausnahme ausgibt.

     [!code-csharp[System.AppDomain.FirstChanceException_howto#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#3)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#3)]

2. Erstellen Sie eine Anwendungsdomäne, und fügen Sie dem <xref:System.AppDomain.FirstChanceException>-Ereignis dieser Anwendungsdomäne den Ereignishandler hinzu. In diesem Beispiel heißt die Anwendungsdomäne `AD1`.

     [!code-csharp[System.AppDomain.FirstChanceException_howto#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#2)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#2)]

     Sie können dieses Ereignis in der Standardanwendungsdomäne auf dieselbe Weise behandeln. Verwenden Sie die statische (`static`) <xref:System.AppDomain.CurrentDomain%2A?displayProperty=nameWithType>-Eigenschaft (`Shared` in Visual Basic) in `Main()`, um einen Verweis auf die Standardanwendungsdomäne abzurufen.

#### <a name="to-demonstrate-first-chance-exception-notifications-in-the-application-domain"></a>So demonstrieren Sie Benachrichtigungen über Ausnahmefehler der ersten Chance in der Anwendungsdomäne

1. Erstellen Sie ein `Worker`-Objekt in der Anwendungsdomäne, die Sie in der vorherigen Prozedur erstellt haben. Die `Worker`-Klasse muss öffentlich und von <xref:System.MarshalByRefObject> abgeleitet sein, wie im vollständigen Beispiel am Ende dieses Artikels dargestellt.

     [!code-csharp[System.AppDomain.FirstChanceException_howto#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#4)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#4)]

2. Rufen Sie eine Methode des `Worker`-Objekts auf, die eine Ausnahme auslöst. In diesem Beispiel wird die `Thrower`-Methode zweimal aufgerufen. Beim ersten Aufruf lautet das Methodenargument `true`, weswegen die Methode ihre eigene Ausnahme abfängt. Beim zweiten Aufruf lautet das Argument `false`, und die `Main()`-Methode fängt die Ausnahme in der Standardanwendungsdomäne ab.

     [!code-csharp[System.AppDomain.FirstChanceException_howto#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#6)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#6)]

3. Platzieren Sie Code in der `Thrower`-Methode, um zu steuern, ob die Methode ihre eigene Ausnahme behandelt.

     [!code-csharp[System.AppDomain.FirstChanceException_howto#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#5)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#5)]

## <a name="example"></a>Beispiel
 Im folgenden Beispiel wird eine Anwendungsdomäne namens `AD1` erstellt und der Anwendungsdomäne des <xref:System.AppDomain.FirstChanceException>-Ereignisses ein Ereignishandler hinzugefügt. Außerdem wird eine Instanz der `Worker`-Klasse in der Anwendungsdomäne erstellt und eine Methode namens `Thrower` aufgerufen, die <xref:System.ArgumentException> auslöst. Je nach dem Wert des Arguments fängt die Methode die Ausnahme entweder ab, oder es tritt ein Fehler bei der Behandlung auf.

 Jedes Mal, wenn die `Thrower`-Methode eine Ausnahme in `AD1` auslöst, wird das <xref:System.AppDomain.FirstChanceException>-Ereignis in `AD1` ausgelöst, und der Ereignishandler zeigt eine Meldung an. Die Runtime sucht nach einem Ausnahmehandler. Im ersten Fall befindet sich der Ausnahmehandler in `AD1`. Im zweiten Fall wird die Ausnahme in `AD1` nicht behandelt und stattdessen in der Standardanwendungsdomäne abgefangen.

> [!NOTE]
> Der Name der Standardanwendungsdomäne ist identisch mit dem Namen der ausführbaren Datei.

 Wenn Sie der Standardanwendungsdomäne einen Handler für das <xref:System.AppDomain.FirstChanceException>-Ereignis hinzufügen, wird das Ereignis ausgelöst und behandelt, bevor die Standardanwendungsdomäne die Ausnahme behandelt. Um dies zu veranschaulichen, fügen Sie den C#-Code `AppDomain.CurrentDomain.FirstChanceException += FirstChanceException;` (in Visual Basic: `AddHandler AppDomain.CurrentDomain.FirstChanceException, FirstChanceException`) am Anfang von `Main()` ein.

 [!code-csharp[System.AppDomain.FirstChanceException_howto#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#1)]
 [!code-vb[System.AppDomain.FirstChanceException_howto#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#1)]

## <a name="see-also"></a>Siehe auch

- <xref:System.AppDomain.FirstChanceException>
