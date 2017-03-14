---
title: "Unable to write to output file &#39;&lt;filename&gt;&#39;: &lt;error&gt; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc31019"
  - "bc31019"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31019"
ms.assetid: 0845b245-11bb-46fd-95ca-f6cef3c318ef
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Unable to write to output file &#39;&lt;filename&gt;&#39;: &lt;error&gt;
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Beim Erstellen der Datei ist ein Fehler aufgetreten.  
  
 Eine Ausgabedatei kann nicht zum Schreiben geöffnet werden.  Die Datei \(oder der Ordner, der die Datei enthält\) kann für die Exklusivnutzung durch einen anderen Prozess geöffnet sein, oder sie ist schreibgeschützt.  
  
 Häufige Situationen, in denen eine Datei exklusiv genutzt wird, sind:  
  
-   Die Anwendung wird bereits ausgeführt und nutzt die Dateien.  Stellen Sie zum Lösen dieses Problems sicher, dass die Anwendung nicht ausgeführt wird.  
  
-   Die Datei wurde in einer anderen Anwendung geöffnet.  Stellen Sie zum Lösen dieses Problems sicher, dass keine andere Anwendung auf die Dateien zugreift.  Es ist nicht immer ersichtlich, welche Anwendung auf Ihre Dateien zugreift; ein Neustart Ihres Computer kann in diesem Fall der einfachste Weg sein, um die Anwendung zu beenden.  
  
 Es reicht aus, dass eine Projektausgabedatei schreibgeschützt ist, um diese Ausnahme auszulösen.  
  
 **Fehler\-ID:** BC31019  
  
### So beheben Sie diesen Fehler  
  
1.  Kompilieren Sie das Programm erneut, um festzustellen, ob der Fehler erneut auftritt.  
  
2.  Wenn der Fehler weiterhin besteht, speichern Sie Ihre Arbeit, und starten Sie [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] erneut.  
  
3.  Wenn der Fehler weiterhin besteht, starten Sie den Computer neu.  
  
4.  Wenn der Fehler erneut auftritt, installieren Sie [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] neu.  
  
5.  Wenn der Fehler auch nach der erneuten Installation auftritt, informieren Sie den Produktsupport von Microsoft.  
  
### So prüfen Sie Dateiattribute im Datei\-Explorer  
  
1.  Öffnen Sie den gewünschten Ordner.  
  
2.  Klicken Sie auf das Symbol **Ansichten**, und wählen Sie **Details**.  
  
3.  Klicken Sie mit der rechten Maustaste auf die Spaltenüberschrift, und wählen Sie aus der Dropdown\-Liste **Attribute** aus.  
  
### So ändern Sie die Attribute einer Datei oder eines Ordners  
  
1.  Klicken Sie im **Datei\-Explorer** mit der rechten Maustaste auf die Datei oder den Ordner, und wählen Sie **Eigenschaften**.  
  
2.  Deaktivieren Sie auf der Registerkarte **Allgemein** im Abschnitt **Attribute** das Kontrollkästchen **Schreibgeschützt**.  
  
3.  Klicken Sie auf **OK**.  
  
## Siehe auch  
 [Sprechen Sie mit uns](/visual-studio/ide/talk-to-us)