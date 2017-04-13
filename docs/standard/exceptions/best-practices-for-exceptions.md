---
title: "Best Practices f&#252;r Ausnahmen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Ausnahmen, Bewährte Methoden"
ms.assetid: f06da765-235b-427a-bfb6-47cd219af539
caps.latest.revision: 28
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 28
---
# Best Practices f&#252;r Ausnahmen
Eine ausgereifte App behandelt Ausnahmen und Fehler, um App\-Abstürze zu verhindern.  In diesem Artikel werden Best Practices für die Behandlung und Erstellung von Ausnahmen beschrieben.  
  
## Behandeln von Ausnahmen  
 Die folgende Liste enthält einige allgemeine Richtlinien zum Behandeln von Ausnahmen in der App.  
  
-   Verwenden Sie Ausnahmebehandlungscode \(`try`\/`catch`\-Blöcke\) angemessen.  Sie können auch programmgesteuert auf einen wahrscheinlich auftretenden Zustand prüfen, ohne die Ausnahmebehandlung zu verwenden.  
  
     **Programmgesteuerte Prüfungen**.  Im folgenden Beispiel wird mit einer `if`\-Anweisung überprüft, ob eine Verbindung geschlossen ist.  Wenn dies nicht der Fall ist, wird im Beispiel die Verbindung getrennt, anstatt eine Ausnahme auszulösen.  
  
     [!code-cpp[Conceptual.Exception.Handling#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#2)]
     [!code-csharp[Conceptual.Exception.Handling#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#2)]
     [!code-vb[Conceptual.Exception.Handling#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#2)]  
  
     **Ausnahmebehandlung**.  Im folgenden Beispiel wird mithilfe eines `try`\/`catch`\-Blocks die Verbindung geprüft und eine Ausnahme ausgelöst, wenn die Verbindung nicht getrennt ist.  
  
     [!code-cpp[Conceptual.Exception.Handling#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#3)]
     [!code-csharp[Conceptual.Exception.Handling#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#3)]
     [!code-vb[Conceptual.Exception.Handling#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#3)]  
  
     Die Wahl der Methode hängt von der erwarteten Häufigkeit des Ereignisses ab.  
  
    -   Verwenden Sie die Ausnahmebehandlung, wenn das Ereignis nicht sehr häufig auftritt, d. h. wenn das Ereignis wirklich außergewöhnlich ist und auf einen Fehler hinweist \(z. B. ein unerwartetes Dateiende\).  Wenn Sie die Ausnahmebehandlung verwenden, wird weniger Code in normalen Bedingungen ausgeführt.  
  
    -   Verwenden Sie die programmgesteuerte Methode der Fehlerüberprüfung, wenn das Ereignis regelmäßig auftritt und als Teil der normalen Programmausführung betrachtet werden kann.  Wenn Sie die programmgesteuerte Fehlerüberprüfung verwenden, wird mehr Code ausgeführt, wenn eine Ausnahme auftritt.  
  
-   Umgeben Sie den Code, der potenzielle Ausnahmen generieren kann, mit `try`\/`catch`\-Blöcken, und verwenden Sie einen `finally`\-Block, um ggf. Ressourcen zu bereinigen.  Auf diese Weise wird die Ausnahme durch die `try`\-Anweisung generiert, durch die `catch`\-Anweisung wird die Ausnahme behandelt und durch die `finally`\-Anweisung werden die Ressourcen geschlossen oder freigegeben, unabhängig davon, ob eine Ausnahme auftritt.  
  
-   Ordnen Sie Ausnahmen in `catch`\-Blöcken immer von der spezifischsten bis zur allgemeinsten an.  Durch dieses Verfahren werden spezifische Ausnahmen behandelt, bevor sie an einen allgemeineren `catch`\-Block übergeben werden.  
  
## Erstellen und Auslösen von Ausnahmen  
 Die folgende Liste enthält Richtlinien zum Erstellen eigener Ausnahmen und zum Zeitpunkt der Auslösung.  Weitere Informationen finden Sie unter [Entwurfsrichtlinien für Ausnahmen](../../../docs/standard/design-guidelines/exceptions.md).  
  
-   Entwerfen Sie Klassen, damit eine Ausnahme niemals während normaler Verwendung ausgelöst wird.  Beispielsweise stellt eine <xref:System.IO.FileStream>\-Klasse Methoden bereit, mithilfe derer bestimmt werden kann, ob das Ende der Datei erreicht wurde.  Dadurch wird die Ausnahme vermieden, die bei dem Versuch ausgelöst wird, nach Erreichen des Dateiendes weiterzulesen.  Das folgende Beispiel zeigt, wie bis zum Dateiende gelesen wird.  
  
     [!code-cpp[Conceptual.Exception.Handling#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#5)]
     [!code-csharp[Conceptual.Exception.Handling#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#5)]
     [!code-vb[Conceptual.Exception.Handling#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#5)]  
  
-   Lösen Sie Ausnahmen aus, anstatt einen Fehlercode oder HRESULT zurückzugeben.  
  
-   Geben Sie bei sehr häufig auftretenden Fehlern "null" zurück, anstatt eine Ausnahme auszulösen.  Ein sehr häufig auftretender Fehler kann als normale Ablaufsteuerung betrachtet werden.  Indem Sie in diesen Fällen NULL zurückgeben, minimieren Sie die Auswirkungen auf die Leistung einer App.  
  
-   Verwenden Sie in erster Linie die vordefinierten .NET Framework\-Ausnahmetypen.  Führen Sie eine neue Ausnahmenklasse nur ein, wenn keine vordefinierte zutrifft.  
  
-   Lösen Sie eine <xref:System.InvalidOperationException>\-Ausnahme aus, wenn eine festgelegte Eigenschaft oder ein Methodenaufruf aufgrund des aktuellen Status des Objekts nicht geeignet ist.  
  
-   Lösen Sie eine <xref:System.ArgumentException>\-Ausnahme aus oder eine von <xref:System.ArgumentException> abgeleitete Klasse aus, wenn ungültige Parameter übergeben werden.  
  
-   Leiten Sie benutzerdefinierte Ausnahmen für die meisten Apps von der <xref:System.Exception>\-Klasse ab.  Durch das Ableiten von der <xref:System.ApplicationException>\-Klasse ergeben sich keine wesentlichen Vorteile.  
  
-   Lassen Sie die Namen von Ausnahmeklassen auf das Wort "Exception" enden.  Beispiel:  
  
     [!code-cpp[Conceptual.Exception.Handling#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#4)]
     [!code-csharp[Conceptual.Exception.Handling#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#4)]
     [!code-vb[Conceptual.Exception.Handling#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#4)]  
  
-   Verwenden Sie in C\# und C\+\+ mindestens die drei allgemeinen Konstruktoren, wenn Sie eigene Ausnahmeklassen erstellen: den Standardkonstruktor, einen Konstruktor, der eine Zeichenfolgenmeldung akzeptiert und einen Konstruktor, der eine Zeichenfolgenmeldung und eine innere Ausnahme akzeptiert.  Ein Beispiel finden Sie unter [Gewusst wie: Erstellen benutzerdefinierter Ausnahmen](../../../docs/standard/exceptions/how-to-create-user-defined-exceptions.md).  
  
    1.  <xref:System.Exception.%23ctor>, der Standardwerte verwendet.  
  
    2.  <xref:System.Exception.%23ctor%28System.String%29>, der eine Zeichenfolgenmeldung akzeptiert.  
  
    3.  <xref:System.Exception.%23ctor%28System.String%2CSystem.Exception%29>, der eine Zeichenfolgenmeldung und eine interne Ausnahme akzeptiert.  
  
-   Stellen Sie beim Erstellen von benutzerdefinierten Ausnahmen sicher, dass Metadaten der Ausnahmen für remote ausgeführten Code verfügbar sind, und zwar auch bei Ausnahmen, die über verschiedene App\-Domänen hinweg auftreten.  Ein Beispiel: App\-Domäne A erstellt App\-Domäne B, die wiederum Code ausführt, der eine Ausnahme auslöst.  Damit die App\-Domäne A die Ausnahme korrekt erfasst und behandelt, muss die Assembly gefunden werden, in der die durch die App\-Domäne B ausgelöste Ausnahme enthalten ist.  Wenn die App\-Domäne B eine Ausnahme auslöst, die in einer Assembly unter ihrer Anwendungsbasis enthalten ist, aber nicht unter der Anwendungsbasis von App\-Domäne A, kann die App\-Domäne A die Ausnahme nicht finden. Daraufhin wird von der Common Language Runtime eine <xref:System.IO.FileNotFoundException>\-Ausnahme ausgelöst.  Um diese Situation zu vermeiden, haben Sie zwei Möglichkeiten, die Assembly mit den Ausnahmeinformationen bereitzustellen:  
  
    -   Legen Sie die Assembly in einer gemeinsamen Anwendungsbasis ab, die sich beide App\-Domänen teilen.  
  
         \- oder \-  
  
    -   Wenn die Domänen keine gemeinsame Anwendungsbasis verwenden, signieren Sie die Assembly, in der die Ausnahmeinformationen enthalten sind, mit einem starken Namen und legen sie in einem globalen Assemblycache ab.  
  
-   Schließen Sie eine lokalisierte Beschreibungszeichenfolge in jeder Ausnahme ein.  Die für den Benutzer sichtbare Fehlermeldung wird von der Beschreibungszeichenfolge der ausgelösten Ausnahme abgeleitet und nicht von der Ausnahmeklasse.  
  
-   Verwenden Sie grammatisch korrekte Fehlermeldungen, einschließlich Zeichensetzung am Satzende.  Jeder Satz in einer Beschreibungszeichenfolge sollte mit einem Punkt beendet werden.  Ein Beispiel für eine geeignete Beschreibungszeichenfolge ist: "Es ist ein Überlauf der Protokolltabelle aufgetreten."  
  
-   Geben Sie <xref:System.Exception>\-Eigenschaften für den programmgesteuerten Zugriff an.  Geben Sie zusätzliche Eigenschaften für eine Ausnahme nur dann zusätzlich zur Beschreibungszeichenfolge an, wenn es ein programmgesteuertes Szenario gibt, in dem dieser Zusatz sinnvoll ist.  Beispielsweise gibt die <xref:System.IO.FileNotFoundException> die <xref:System.IO.FileNotFoundException.FileName%2A>\-Eigenschaft an.  
  
-   Die Stapelüberwachung beginnt mit der Anweisung, bei der die Ausnahme ausgelöst wurde, und endet mit der `catch`\-Anweisung, mit der die Ausnahme abgefangen wird.  Achten Sie auf diesen Umstand, wenn Sie eine `throw`\-Anweisung platzieren.  
  
-   Verwenden Sie Methoden zum Generieren von Ausnahmen.  Es ist üblich, dass eine Klasse von unterschiedlichen Punkten in der Implementierung aus die gleiche Ausnahme auslöst.  Verwenden Sie Hilfsmethoden, die eine Ausnahme erstellen und zurückgeben, um ausufernden Code zu vermeiden.  Beispiel:  
  
     [!code-cpp[Conceptual.Exception.Handling#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#6)]
     [!code-csharp[Conceptual.Exception.Handling#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#6)]
     [!code-vb[Conceptual.Exception.Handling#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#6)]  
  
     Sie können auch den Ausnahmekonstruktor verwenden, um eine Ausnahme zu erstellen.  Dies ist bei globalen Ausnahmeklassen wie der <xref:System.ArgumentException>\-Klasse eher angebracht.  
  
-   Löschen Sie Zwischenergebnisse, wenn Sie eine Ausnahme auslösen.  Aufrufer sollten davon ausgehen können, dass keine Nebeneffekte auftreten, wenn eine Ausnahme von einer Methode ausgelöst wird.  
  
## Siehe auch  
 [Ausnahmen](../../../docs/standard/exceptions/index.md)