---
title: "Garbage Collection Notifications | Microsoft Docs"
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
  - "garbage collection, notifications"
ms.assetid: e12d8e74-31e3-4035-a87d-f3e66f0a9b89
caps.latest.revision: 23
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 23
---
# Garbage Collection Notifications
Es gibt Situationen, in denen eine vollständige Garbage Collection werden \(das heißt, eine Collection der Generation 2\) von der Common Language Runtime die Leistung nachteilig beeinflussen.  Das kann besonders für Server, die eine große Zahl von Anfragen verarbeiten, ein Problem darstellen. In diesem Fall kann eine lange Garbage Collection einen Anforderungstimeout verursachen.  Um vollständige Collections in kritischen Zeiträumen zu verhindern, können Sie sich über anstehende Collections benachrichtigen lassen und dann entsprechende Maßnahmen ergreifen, um die Arbeitsauslastung auf eine andere Serverinstanz umzuleiten.  Sie können auch selbst eine Collection auslösen, wenn die aktuelle Serverinstanz keine Anfragen verarbeiten muss.  
  
 Die <xref:System.GC.RegisterForFullGCNotification%2A>\-Methode wird für die Auslösung einer Benachrichtigung registriert, wenn die Laufzeit ermittelt, dass eine vollständige Garbage Collection ansteht.  Diese Benachrichtigung besteht aus zwei Teilen: dem Anstehen einer vollständigen Garbage Collection und dem Abschluss der vollständigen Garbage Collection.  
  
> [!WARNING]
>  Nur blockierende Garbage Collections lösen Benachrichtigungen aus.  Wenn das Konfigurationselement [\<gcConcurrent\>](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) aktiviert ist, werden Garbage Collections im Hintergrund keine Benachrichtigungen aus.  
  
 Verwenden Sie die <xref:System.GC.WaitForFullGCApproach%2A>\- Methode und <xref:System.GC.WaitForFullGCComplete%2A>\-Methode, um zu ermitteln, wann eine Benachrichtigung ausgelöst wurde.  Sie verwenden diese Methoden normalerweise in einer `while`\-Schleife, um fortlaufend eine <xref:System.GCNotificationStatus>\-Enumeration mit dem Status der Benachrichtigung zu erhalten.  Wenn dieser Wert <xref:System.GCNotificationStatus> ist, können Sie folgendermaßen vorgehen:  
  
-   Als Reaktion auf eine Benachrichtigung, die mit der <xref:System.GC.WaitForFullGCApproach%2A>\-Methode abgerufen wurde, können Sie die Arbeitsauslastung umleiten und gegebenenfalls selbst eine Collection auslösen.  
  
-   Als Reaktion auf eine Benachrichtigung, die mit der <xref:System.GC.WaitForFullGCComplete%2A>\-Methode abgerufen wurde, können Sie die aktuelle Serverinstanz erneut für die Verarbeitung von Anforderungen verfügbar machen.  Sie können auch Informationen sammeln.  Zum Beispiel können Sie die <xref:System.GC.CollectionCount%2A>\-Methode verwenden, um die Anzahl der Collections aufzuzeichnen.  
  
 Beschreibt, wie die <xref:System.GC.WaitForFullGCApproach%2A>\-Methode und die <xref:System.GC.WaitForFullGCComplete%2A>\-Methode zusammenwirken.  Wenn Sie eine Methode ohne die andere verwenden, können unbestimmte Ergebnisse auftreten.  
  
## Vollständige Garbage Collection  
 Die Laufzeit veranlasst eine vollständige Garbage Collection, wenn eines der folgenden Szenarien zutrifft:  
  
-   Es wurde genügend Speicher in Generation 2 höher gestuft, um die nächste Collection von Generation 2 auszulösen.  
  
-   Es wurde genügend Speicher in den großen Objektheap höher gestuft, um die nächste Collection der Generation 2 auszulösen.  
  
-   Eine Collection der Generation 1 wird aufgrund anderer Faktoren zu einer Collection der Generation 2 eskaliert.  
  
 Die Schwellenwerte, die Sie in der <xref:System.GC.RegisterForFullGCNotification%2A>\-Methode angeben, gelten für die ersten zwei Szenarios.  Im ersten Szenario werden Sie jedoch aus zwei Gründen nicht immer die Benachrichtigung über die den Schwellenwerten entsprechende Zeit erhalten, die Sie festgelegt haben:  
  
-   Die Laufzeit überprüft aus Leistungsgründen nicht jede kleine Objektzuordnung.  
  
-   Nur Collections der Generation 1 stufen Speicher in die Generation 2 herauf.  
  
 Das dritte Szenario trägt auch zur Ungewissheit bei, wann Sie die Benachrichtigung empfangen.  Obwohl dies keine Garantie ist, ist es doch ein sinnvoller Weg, die Auswirkungen einer unerwünschten vollständigen Garbage Collection zu mindern, indem die Anforderungen während dieser Zeit umgeleitet werden, oder Sie selbst eine Collection vornehmen, wenn diese zeitlich passender ist.  
  
## Parameter für den Benachrichtigungsschwellenwert  
 Die <xref:System.GC.RegisterForFullGCNotification%2A>\-Methode verfügt über zwei Parameter, die die Schwellenwerte für Objekte der Generation 2 und den Heap für große Objekte festlegt.  Wenn diese Werte erfüllt werden, sollte eine Garbage Collection\-Benachrichtigung ausgelöst werden.  In der folgenden Tabelle werden diese Parameter beschrieben.  
  
|Parameter|**Beschreibung**|  
|---------------|----------------------|  
|`maxGenerationThreshold`|Eine Zahl zwischen 1 und 99, die auf Grundlage der in die Generation 2 hochgestuften Objekte angibt, wann die Benachrichtigung ausgelöst werden soll.|  
|`largeObjectHeapThreshold`|Eine Zahl zwischen 1 und 99, die auf Grundlage der im großen Objektheap reservierten Objekte angibt, wann die Benachrichtigung ausgelöst werden soll.|  
  
 Wenn Sie einen Wert festlegen, der zu hoch ist, erhalten Sie mit hoher Wahrscheinlichkeit eine Benachrichtigung. Es kann jedoch eine zu lange Wartezeit auftreten, bevor die Laufzeit eine Collection veranlasst.  Wenn Sie selbst eine Collection auslösen, können Sie mehr Objekte freigeben, als dies bei einer Collection durch die Laufzeit der Fall wäre.  
  
 Wenn Sie einen Wert angeben, der zu niedrig ist, veranlasst die Laufzeit möglicherweise eine Collection, bevor Sie eine Benachrichtigung erhalten.  
  
## Beispiel  
  
### **Beschreibung**  
 Im folgenden Beispiel verarbeitet eine Gruppe von Servern eingehende Webanforderungen.  Um die Arbeitslast für das Verarbeiten von Anforderungen zu simulieren, werden einer <xref:System.Collections.Generic.List%601>\-Auflistung Bytearrays hinzugefügt.  Jeder Server registriert sich für eine Garbage Collection\-Benachrichtigung und startet einen Thread für die `WaitForFullGCProc`\-Benutzermethode, um die <xref:System.GCNotificationStatus>\-Enumeration, die von den <xref:System.GC.WaitForFullGCApproach%2A> und den <xref:System.GC.WaitForFullGCComplete%2A> Methoden zurückgegeben wird, ständig zu überwachen.  
  
 Die <xref:System.GC.WaitForFullGCApproach%2A>\- Methode und die <xref:System.GC.WaitForFullGCComplete%2A>\-Methode rufen ihre jeweiligen Benutzermethoden zur Ereignisbehandlung auf, wenn eine Benachrichtigung ausgelöst wird:  
  
-   `OnFullGCApproachNotify`  
  
     Diese Methode ruft die `RedirectRequests`\-Benutzermethode auf, die den Server für Anforderungswarteschlangen anweist, keine weiteren Anforderungen an den Server zu senden.  Dies wird durch Festlegen der Klassenebenenvariable `bAllocate` auf `false` simuliert, sodass keine weiteren Objekte zugewiesen werden.  
  
     Danach wird die `FinishExistingRequests`\-Benutzermethode aufgerufen, um die ausstehenden Serveranforderungen zu verarbeiten.  Dies wird durch Löschen der <xref:System.Collections.Generic.List%601>\-Auflistung simuliert.  
  
     Schließlich wird eine Garbage Collection veranlasst, da die Arbeitslast gering ist.  
  
-   `OnFullGCCompleteNotify`  
  
     Diese Methode ruft die `AcceptRequests`\- Benutzermethode dazu auf, wieder Anforderungen anzunehmen, da der Server nicht mehr für eine vollständige Garbage Collection anfällig ist.  Diese Aktion wird simuliert, indem die `bAllocate`\-Variable auf `true` festgelegt wird, sodass Objekte wieder der <xref:System.Collections.Generic.List%601>\-Auflistung zugewiesen werden können.  
  
 Der folgende Code enthält die `Main`\-Methode des Beispiels.  
  
 [!code-cpp[GCNotification#2](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#2)]
 [!code-csharp[GCNotification#2](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#2)]
 [!code-vb[GCNotification#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#2)]  
  
 Der folgende Code enthält die `WaitForFullGCProc`\-Benutzermethode mit einer kontinuierlichen \<legacyBold\>While\<\/legacyBold\>\-Schleife, um eine Überprüfung auf Garbage Collection\-Benachrichtigungen durchzuführen.  
  
 [!code-cpp[GCNotification#8](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#8)]
 [!code-csharp[GCNotification#8](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#8)]
 [!code-vb[GCNotification#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#8)]  
  
 Der folgende Code enthält die `OnFullGCApproachNotify`\-Methode, wie aufgerufen von der  
  
 `WaitForFullGCProc`\-Methode.  
  
 [!code-cpp[GCNotification#5](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#5)]
 [!code-csharp[GCNotification#5](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#5)]
 [!code-vb[GCNotification#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#5)]  
  
 Der folgende Code enthält die `OnFullGCApproachComplete`\-Methode, wie aufgerufen von der  
  
 `WaitForFullGCProc`\-Methode.  
  
 [!code-cpp[GCNotification#6](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#6)]
 [!code-csharp[GCNotification#6](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#6)]
 [!code-vb[GCNotification#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#6)]  
  
 Der folgende Code enthält die Benutzermethoden, die von der `OnFullGCApproachNotify`\-Methode und `OnFullGCCompleteNotify`\-Methode aufgerufen werden.  Die Benutzermethode leitet Anforderungen um, schließt vorhandene Anforderungen ab und nimmt Anforderungen wieder auf, nachdem eine vollständige Garbage Collection erfolgt ist.  
  
 [!code-cpp[GCNotification#9](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#9)]
 [!code-csharp[GCNotification#9](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#9)]
 [!code-vb[GCNotification#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#9)]  
  
 Im Folgenden finden Sie das gesamte Codebeispiel.  
  
 [!code-cpp[GCNotification#1](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#1)]
 [!code-csharp[GCNotification#1](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#1)]
 [!code-vb[GCNotification#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#1)]  
  
## Siehe auch  
 [Garbage Collection](../../../docs/standard/garbage-collection/index.md)