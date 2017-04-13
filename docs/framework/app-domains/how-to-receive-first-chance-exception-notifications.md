---
title: "Gewusst wie: Empfangen von Ausnahmebenachrichtigungen (erste Chance) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Ausnahmen, Benachrichtigungen (erste Chance)"
  - "Ausnahmebenachrichtigungen (erste Chance)"
ms.assetid: 66f002b8-a97d-4a6e-a503-2cec01689113
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Empfangen von Ausnahmebenachrichtigungen (erste Chance)
Sie erhalten vom <xref:System.AppDomain.FirstChanceException>\-Ereignis der <xref:System.AppDomain>\-Klasse eine Benachrichtigung, dass eine Ausnahme ausgelöst wurde, bevor von der Common Language Runtime die Suche nach Ausnahmehandlern gestartet wurde.  
  
 Das Ereignis wird auf der Ebene der Anwendungsdomäne ausgelöst.  Ein Ausführungsthread kann mehrere Anwendungsdomänen durchlaufen, damit eine Ausnahme, die in einer Anwendungsdomäne nicht behandelt wurde, in einer anderen Anwendungsdomäne behandelt werden kann.  Die Benachrichtigung wird so lange in den Anwendungsdomänen mit einem Handler für das Ereignis ausgegeben, bis die Ausnahme von einer Anwendungsdomäne behandelt wird.  
  
 In den Prozeduren und den Beispielen in diesem Artikel wird veranschaulicht, wie Ausnahmebenachrichtigungen \(erste Chance\) in einem einfachen Programm, das eine Anwendungsdomäne aufweist, und in einer vom Benutzer erstellten Anwendungsdomäne empfangen werden.  
  
 Ein komplexeres Beispiel, das mehrere Anwendungsdomänen umfasst, finden Sie im Beispiel für das <xref:System.AppDomain.FirstChanceException>\-Ereignis.  
  
## Empfangen von Ausnahmebenachrichtigungen \(erste Chance\) in der Standardanwendungsdomäne  
 Im folgenden Verfahren \(dem Einstiegspunkt für die Anwendung\) wird die `Main()`\-Methode in der Standardanwendungsdomäne ausgeführt.  
  
#### So werden Ausnahmebenachrichtigungen \(erste Chance\) in der Standardanwendungsdomäne dargestellt  
  
1.  Definieren Sie einen Ereignishandler mit einer Lambda\-Funktion für das <xref:System.AppDomain.FirstChanceException>\-Ereignis, und fügen Sie ihn an das Ereignis an.  In diesem Beispiel gibt der Ereignishandler den Namen der Anwendungsdomäne, in der das Ereignis behandelt wurde, und die <xref:System.Exception.Message%2A>\-Eigenschaft der Ausnahme aus.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#2)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#2)]  
  
2.  Lösen Sie eine Ausnahme aus, und fangen Sie sie ab.  Bevor der Ausnahmehandler von der Runtime gefunden wird, wird das <xref:System.AppDomain.FirstChanceException>\-Ereignis ausgelöst und eine Meldung angezeigt.  Dieser Meldung folgt die vom Ausnahmehandler angezeigte Meldung.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#3)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#3)]  
  
3.  Lösen Sie eine Ausnahme aus, fangen Sie sie aber nicht ab.  Bevor der Ausnahmehandler von der Runtime gesucht wird, wird das <xref:System.AppDomain.FirstChanceException>\-Ereignis ausgelöst und eine Meldung angezeigt.  Es ist kein Ausnahmehandler vorhanden. Die Anwendung wird beendet.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#4)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#4)]  
  
     Der Code in den ersten drei Schritten dieses Verfahrens bildet eine vollständige Konsolenanwendung.  Die Ausgabe der Anwendung variiert abhängig vom Namen der EXE\-Datei, da sich der Name der Standardanwendungsdomäne aus dem Namen und der Erweiterung der EXE\-Datei zusammensetzt.  Im Folgenden sehen Sie ein Beispiel für die Ausgabe.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#5)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#5)]  
  
## Empfangen von Ausnahmebenachrichtigungen \(erste Chance\) in einer anderen Anwendungsdomäne  
 Wenn das Programm mehr als eine Anwendungsdomäne enthält, können Sie auswählen, welche Anwendungsdomänen Benachrichtigungen empfangen sollen.  
  
#### So empfangen Sie Ausnahmebenachrichtigungen \(erste Chance\) in einer von Ihnen erstellten Anwendungsdomäne  
  
1.  Definieren Sie einen Ereignishandler für das <xref:System.AppDomain.FirstChanceException>\-Ereignis.  In diesem Beispiel wird eine `static`\-Methode verwendet \(`Shared`\-Methode in Visual Basic\), die den Namen der Anwendungsdomäne, in der das Ereignis behandelt wurde, sowie die <xref:System.Exception.Message%2A>\-Eigenschaft der Ausnahme druckt.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#3)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#3)]  
  
2.  Erstellen Sie eine Anwendungsdomäne, und fügen Sie dem <xref:System.AppDomain.FirstChanceException>\-Ereignis den Ereignishandler für diese Anwendungsdomäne hinzu.  In diesem Beispiel trägt die Anwendungsdomäne die Bezeichnung `AD1`.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#2)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#2)]  
  
     Sie können dieses Ereignis in der Standardanwendungsdomäne auf dieselbe Weise behandeln.  Verwenden Sie die `static` \(`Shared` in Visual Basic\) <xref:System.AppDomain.CurrentDomain%2A?displayProperty=fullName>\-Eigenschaft in `Main()`, um einen Verweis auf die Standardanwendungsdomäne abzurufen.  
  
#### So werden Ausnahmebenachrichtigungen \(erste Chance\) in der Anwendungsdomäne dargestellt  
  
1.  Erstellen Sie ein `Worker`\-Objekt in der Anwendungsdomäne, die Sie im vorherigen Verfahren erstellt haben.  Die `Worker`\-Klasse muss öffentlich sein und sich von <xref:System.MarshalByRefObject> ableiten, wie im vollständigen Beispiel am Ende dieses Artikels gezeigt.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#4)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#4)]  
  
2.  Rufen Sie eine Methode des `Worker`\-Objekts auf, die eine Ausnahme auslöst.  In diesem Beispiel wird die `Thrower`\-Methode zweimal aufgerufen.  Beim ersten Mal ist das Methodenargument auf `true` festgelegt, wodurch von der Methode die eigene Ausnahme abgefangen wird.  Beim zweiten Mal ist das Argument auf `false` festgelegt, und von der `Main()`\-Methode wird die Ausnahme in der Standardanwendungsdomäne abgefangen.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#6)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#6)]  
  
3.  Platzieren Sie Code in der `Thrower`\-Methode, um zu steuern, ob von der Methode eine eigene Ausnahme behandelt werden soll.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#5)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#5)]  
  
## Beispiel  
 Im folgenden Beispiel wird eine Anwendungsdomäne mit der Bezeichnung `AD1` erstellt und dem <xref:System.AppDomain.FirstChanceException>\-Ereignis der Anwendungsdomäne ein Ereignishandler hinzugefügt.  Zusätzlich wird eine Instanz der `Worker`\-Klasse in der Anwendungsdomäne erstellt und eine `Thrower`\-Methode aufgerufen, von der eine <xref:System.ArgumentException> ausgelöst wird.  Je nach Wert des Arguments wird von der Methode die Ausnahme entweder abgefangen oder nicht behandelt.  
  
 Jedes Mal, wenn von der `Thrower`\-Methode eine Ausnahme in `AD1` ausgelöst wird, wird das <xref:System.AppDomain.FirstChanceException>\-Ereignis in `AD1` ausgelöst, und vom Ereignishandler wird eine Meldung angezeigt.  Anschließend wird von der Laufzeit nach einem Ausnahmehandler gesucht.  Im ersten Fall wird der Ausnahmehandler in `AD1` gefunden.  Im zweiten Fall wird die Ausnahme in `AD1` nicht behandelt und stattdessen in der Standardanwendungsdomäne abgefangen.  
  
> [!NOTE]
>  Der Name der Standardanwendungsdomäne entspricht dem Namen der EXE\-Datei.  
  
 Wenn Sie der Standardanwendungsdomäne einen Handler für das <xref:System.AppDomain.FirstChanceException>\-Ereignis hinzufügen, wird das Ereignis ausgelöst und behandelt, bevor die Ausnahme von der Standardanwendungsdomäne behandelt wird.  Fügen Sie den C\#\-Code `AppDomain.CurrentDomain.FirstChanceException += FirstChanceException;` \(in Visual Basic `AddHandler AppDomain.CurrentDomain.FirstChanceException, FirstChanceExceptio`\) am Anfang von `Main()` ein, um diesen Effekt zu erzielen.  
  
 [!code-csharp[System.AppDomain.FirstChanceException_howto#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#1)]
 [!code-vb[System.AppDomain.FirstChanceException_howto#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#1)]  
  
## Kompilieren des Codes  
  
-   Dieses Beispiel ist eine Befehlszeilenanwendung.  Zum Kompilieren und Ausführen dieses Codes in [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)] fügen Sie den C\#\-Code am Ende von `Console.ReadLine();``Main()`\(in Visual Basic `Console.ReadLine()`\) ein. So wird verhindert, dass das Befehlsfenster geschlossen wird, bevor Sie die Ausgabe lesen können.  
  
## Siehe auch  
 <xref:System.AppDomain.FirstChanceException>