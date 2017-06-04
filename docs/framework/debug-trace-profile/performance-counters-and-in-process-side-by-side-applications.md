---
title: "Performance Counters and In-Process Side-By-Side Applications | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "performance counters"
  - "performance counters,and in-process side-by-side applications"
  - "performance,.NET Framework applications"
  - "performance monitoring,counters"
ms.assetid: 6888f9be-c65b-4b03-a07b-df7ebdee2436
caps.latest.revision: 26
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 26
---
# Performance Counters and In-Process Side-By-Side Applications
Der Systemmonitor \(Perfmon.exe\) ermöglicht eine laufzeitbasierte Unterscheidung der Leistungsindikatoren.  In diesem Thema wird die Registrierungsänderung beschrieben, die erforderlich ist, um diese Funktion zu aktivieren.  
  
## Standardverfahren  
 Die Leistungsindikatoren werden vom Systemmonitor standardmäßig anwendungsbasiert angezeigt.  Es gibt jedoch zwei Szenarios, in denen dies problematisch ist:  
  
-   Wenn Sie zwei Anwendungen überwachen, die den gleichen Namen haben.  Wenn beide Anwendungen beispielsweise myapp.exe heißen, wird eine Anwendung als **myapp** und die andere Anwendung als **myapp\#1** in der Spalte **Instanz** angezeigt.  In diesem Fall ist es schwierig, einen Leistungsindikator einer bestimmten Anwendung zuzuordnen.  Es ist nicht klar, ob sich Daten, die für **myapp\#1** erfasst wurden, auf die erste oder auf die zweite myapp.exe\-Anwendung beziehen.  
  
-   Wenn eine Anwendung mehrere Instanzen der Common Language Runtime verwendet.  [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] unterstützt prozessinterne parallele Hostingszenarien, sodass in einem Prozess oder einer Anwendung mehrere Instanzen der Common Language Runtime geladen werden können.  Wenn eine einzelne Awendung \(myapp.exe\) zwei Laufzeitinstanzen lädt, werden diese standardmäßig in der Spalte **Instanz** als **myapp** und **myapp\#1** angezeigt.  In diesem Fall ist unklar, ob sich **myapp** und **myapp\#1** auf zwei Anwendungen mit dem gleichen Namen oder auf die gleiche Anwendung mit zwei Laufzeiten beziehen.  Wenn mehrere Anwendungen mit dem gleichen Namen mehrere Laufzeiten laden, entstehen weitere Mehrdeutigkeiten.  
  
 Sie können einen Registrierungsschlüssel festlegen, um diese Mehrdeutigkeit auszuschließen.  Bei Anwendungen, die mit [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] entwickelt wurden, werden in der Spalte **Instanz** ein Prozessbezeichner sowie ein Bezeichner für die Laufzeitinstanz an den Namen der Anwendung angefügt.  Anstelle *application* oder *application* bezeichnet, sondern mit die Anwendung jetzt als *runtimeID* \_`r`*application*\_`p`*processID* in der Spalte **Instanz** identifiziert.  Wenn eine Anwendung mit einer früheren Version der Common Language Runtime entwickelt wurde, wird diese Instanz als *application\_*`p`*processID* dargestellt, vorausgesetzt, dass [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] installiert ist.  
  
## Leistungsindikatoren für prozessinterne parallele Anwendungen  
 Um Leistungsindikatoren für mehrere Common Language Runtime\-Versionen zu behandeln, die in einer einzelnen Anwendung gehostet werden, müssen Sie eine einzelne Registrierungsschlüsseleinstellung ändern, wie in der folgenden Tabelle veranschaulicht.  
  
|||  
|-|-|  
|Schlüsselname|HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Services\\.NETFramework\\Performance|  
|Wertname|ProcessNameFormat|  
|Werttyp|REG\_DWORD|  
|Wert|1 \(0x00000001\)|  
  
 Der Wert 0 für `ProcessNameFormat` gibt an, dass das Standardverhalten aktiviert ist, d. h., "Perfmon.exe" zeigt Leistungsindikatoren pro Anwendung an.  Wenn Sie diesen Wert auf 1 festlegen, vereindeutigt "Perfmon.exe" mehrere Versionen einer Anwendung und stellt Leistungsindikatoren pro Runtime bereit.  Ein anderer Wert für die `ProcessNameFormat`\-Registrierungsschlüsseleinstellung wird nicht unterstützt und ist für eine zukünftige Verwendung reserviert.  
  
 Nachdem Sie die `ProcessNameFormat`\-Registrierungsschlüsseleinstellung aktualisiert haben, müssen Sie "Perfmon.exe" oder andere Consumer von Leistungsindikatoren neu starten, damit die Funktion zum Benennen neuer Instanzen korrekt funktioniert.  
  
 Das folgende Beispiel zeigt, wie Sie den `ProcessNameFormat`\-Wert programmgesteuert ändern können.  
  
 [!code-csharp[Conceptual.PerfCounters.InProSxS#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.perfcounters.inprosxs/cs/regsetting1.cs#1)]
 [!code-vb[Conceptual.PerfCounters.InProSxS#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.perfcounters.inprosxs/vb/regsetting1.vb#1)]  
  
 Wenn Sie diese Registrierungsänderung vornehmen, werden in Perfmon.exe die Namen der Anwendungen, die auf [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] als *runtimeID*\_`r`*application*\_`p`*processID*, wobei *application* der Name der Anwendung ist, *processID* die Prozess\-ID der Anwendung als Ziel und *runtimeID* ein Common Language Runtime\-Bezeichner ist.  Wenn z. B. zwei Instanzen der Common Language Runtime von der Anwendung "myapp.exe" geladen werden, kann "Perfmon.exe" eine Instanz als "myapp\_p1416\_r10" und die andere Instanz als "myapp\_p3160\_r10" identifizieren.  Der Laufzeitbezeichner unterscheidet nur zwischen den Laufzeiten innerhalb eines Prozesses und enthält keine darüber hinaus gehenden Laufzeitinformationen. \(Der Laufzeitbezeichner hat beispielsweise keinen Bezug zur Version oder zur SKU der Laufzeit.\)  
  
 Wenn [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] installiert ist, wirkt sich die Registrierungsänderung auch auf Anwendungen aus, die mit früheren Versionen von .NET Framework entwickelt wurden.  Diese werden in Perfmon.exe als *application\_*`p`*processID*, wobei *application* der Anwendungsname darstellt und *processID* die Prozess\-ID ist.  Wenn beispielsweise die Leistungsindikatoren der gleichnamigen Anwendungen myapp.exe und myapp.exe überwacht werden, kann eine Anwendung als myapp\_p23900 und die andere Anwendung als myapp\_p24908 angezeigt werden.  
  
> [!NOTE]
>  Der Prozessbezeichner beseitigt die Mehrdeutigkeit bei der Auflösung zweier Anwendungen mit dem gleichen Namen, die eine frühere Versionen der Laufzeit verwenden.  Ein Laufzeitbezeichner ist für frühere Versionen nicht erforderlich, da frühere Versionen der Common Language Runtime keine parallelen Szenarios unterstützen.  
  
 Wenn [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] nicht vorhanden ist oder deinstalliert wurde, hat das Festlegen des Registrierungsschlüssels keine Auswirkungen.  Dies bedeutet, dass zwei Anwendungen mit dem gleichen Namen auch weiterhin, um als *application* und als *application\#1* in Perform.exe angezeigt werden \(beispielsweise, als **myapp** und **myapp\#1**\).