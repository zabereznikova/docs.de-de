---
title: "Gewusst wie: Durchlaufen einer Verzeichnisstruktur (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Dateiiteration [C#]"
  - "Durchlaufen von Ordnern [C#]"
ms.assetid: c4be4a75-6b1b-46a7-9d38-bab353091ed7
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gewusst wie: Durchlaufen einer Verzeichnisstruktur (C#-Programmierhandbuch)
Der Ausdruck "Durchlaufen einer Verzeichnisstruktur" bedeutet, auf jede Datei in einem verschachtelten Unterverzeichnis in einem angegebenen Stammordner zuzugreifen.  Sie müssen nicht unbedingt jede Datei öffnen.  Sie können einfach den Namen der Datei oder des Unterverzeichnisses als `string` oder zusätzliche Informationen in Form eines <xref:System.IO.FileInfo?displayProperty=fullName>\- Objekts oder <xref:System.IO.DirectoryInfo?displayProperty=fullName>\-Objekts abrufen.  
  
> [!NOTE]
>  In Windows sind die Begriffe "Verzeichnis" und "Ordner" austauschbar.  In den meisten Dokumentationen und Benutzeroberflächentexten wird der Begriff "Ordner" verwendet, die [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Klassenbibliothek verwendet jedoch den Begriff "Verzeichnis".  
  
 Im einfachsten Fall, bei dem Sie ganz sicher sind, dass Sie Zugriffsberechtigungen für alle Verzeichnisse in einem bestimmten Stammverzeichnis haben, können Sie das `System.IO.SearchOption.AllDirectories`\-Flag verwenden.  Dieses Flag gibt alle geschachtelten Unterverzeichnisse zurück, die mit dem angegebenen Muster übereinstimmen.  Im folgenden Beispiel wird die Verwendung dieses Flags dargestellt.  
  
```c#  
root.GetDirectories("*.*", System.IO.SearchOption.AllDirectories);  
```  
  
 Der Schwachpunkt bei dieser Methode besteht darin, dass die Methode fehlschlägt und keine Verzeichnisse zurückgibt, falls eines der Unterverzeichnisse im angegebenen Stammverzeichnis <xref:System.IO.DirectoryNotFoundException> oder <xref:System.UnauthorizedAccessException> auslöst.  Dasselbe gilt, wenn Sie die <xref:System.IO.DirectoryInfo.GetFiles%2A>\-Methode verwenden.  Wenn Sie diese Ausnahmen für bestimmte Unterverzeichnisse umgehen müssen, müssen Sie die Verzeichnisstruktur manuell durchlaufen, wie in den folgenden Beispielen dargestellt.  
  
 Wenn Sie eine Verzeichnisstruktur manuell durchlaufen, können Sie zuerst die Unterverzeichnisse \(*Durchlauf vor der Sortierung*\) oder zuerst die Dateien \(*Durchlauf nach der Sortierung*\) durchlaufen.  Wenn Sie einen Durchlauf vor der Sortierung ausführen, durchlaufen Sie die gesamte Verzeichnisstruktur unter dem aktuellen Verzeichnis vor den Dateien, die sich direkt im diesem Verzeichnis befinden.  In den Beispielen weiter unten in diesem Dokument wird ein Durchlauf nach der Sortierung ausgeführt. Sie können diesen aber problemlos in einen Durchlauf vor der Sortierung ändern.  
  
 Außerdem können Sie zwischen einem Rekursions\- und einem stapelbasierten Durchlauf wählen.  In den Beispielen weiter unten in diesem Dokument werden beide Verfahren erläutert.  
  
 Falls Sie verschiedene Operationen für Dateien und Ordner durchführen müssen, können Sie diese Beispiele in einer modularen Struktur halten. Gestalten Sie die Operation dazu in separate Funktionen um, die Sie mit einem einzelnen Delegaten aufrufen können.  
  
> [!NOTE]
>  NTFS\-Dateisysteme können *Reparse Points* in Form von *Abzweigungspunkten*, *symbolischen Links* und *festen Links* enthalten.  Die .NET Framework\-Methoden, wie <xref:System.IO.DirectoryInfo.GetFiles%2A> und <xref:System.IO.DirectoryInfo.GetDirectories%2A> geben keine Unterverzeichnisse unterhalb eines Analysepunkts zurück.  Dieses Verhalten schützt vor dem Risiko einer Endlosschleife, wenn zwei Reparse Points aufeinander verweisen.  Im Allgemeinen sollten Sie extrem vorsichtig bei der Verwendung von Reparse Points sein, um sicherzustellen, dass Sie nicht unbeabsichtigterweise Dateien ändern oder löschen.  Wenn Sie Reparse Points genau steuern möchten, verwenden Sie den Plattformaufruf oder systemeigenen Code zum direkten Aufrufen der entsprechenden Win32\-Dateisystemmethoden.  
  
## Beispiel  
 Im folgenden Beispiel wird dargestellt, wie eine Verzeichnisstruktur mit Rekursion durchlaufen wird.  Der rekursive Ansatz ist elegant. Jedoch besteht die Gefahr, dass eine Stapelüberlaufausnahme verursacht wird, falls es sich um eine große und tief verschachtelte Verzeichnisstruktur handelt.  
  
 Die besonderen Ausnahmen für jede Datei und jeden Ordner und die besonderen Aktionen, die für jede Datei und jeden Ordner ausgeführt werden, werden lediglich als Beispiel dargestellt.  Sie sollten diesen Code ändern, um Ihre speziellen Anforderungen zu erfüllen.  Weitere Informationen finden Sie in den Kommentaren im Code.  
  
 [!code-cs[csFilesandFolders#1](../../../csharp/programming-guide/file-system/codesnippet/CSharp/csFilesFolders/FileIteration.cs#1)]  
  
## Beispiel  
 Im folgenden Beispiel wird dargestellt, wie Verzeichnisse und Ordner in einer Verzeichnisstruktur ohne Rekursion durchlaufen werden.  Bei dieser Methode wird der generische <xref:System.Collections.Generic.Stack%601>\-Auflistungstyp verwendet, bei dem es sich um einen LIFO\-Stapel handelt.  
  
 Die besonderen Ausnahmen für jede Datei und jeden Ordner und die besonderen Aktionen, die für jede Datei und jeden Ordner ausgeführt werden, werden lediglich als Beispiel dargestellt.  Sie sollten diesen Code ändern, um Ihre speziellen Anforderungen zu erfüllen.  Weitere Informationen finden Sie in den Kommentaren im Code.  
  
 [!code-cs[csFilesandFolders#2](../../../csharp/programming-guide/file-system/codesnippet/CSharp/csFilesFolders/FileIteration.cs#2)]  
  
 In der Regel ist es zu zeitaufwändig, jeden Ordner zu testen, um zu ermitteln, ob Ihre Anwendung über die Berechtigungen zum Öffnen verfügt.  Im Codebeispiel wird deshalb nur dieser Teil der Operation in einen `try/catch`\-Block eingeschlossen.  Sie können den `catch`\-Block so ändern, dass Ihre Berechtigungen bei verweigertem Zugriff auf einen Ordner erhöht werden. Anschließend können Sie erneut darauf zugreifen.  Fangen Sie als Regel einfach die Ausnahmen ab, die Sie verarbeiten können, ohne Ihre Anwendung in einem unbekannten Zustand zu lassen.  
  
 Falls Sie den Inhalt einer Verzeichnisstruktur entweder im Arbeitsspeicher oder auf Festplatte speichern müssen, speichern Sie am besten nur die <xref:System.IO.FileSystemInfo.FullName%2A>\-Eigenschaft \(vom Typ `string`\) für jede Datei.  Sie können diese Zeichenfolge dann verwenden, um ggf. ein neues <xref:System.IO.FileInfo>\-Objekt oder <xref:System.IO.DirectoryInfo>\-Objekt zu erstellen, oder eine Datei öffnen, für die eine weitere Bearbeitung erforderlich ist.  
  
## Robuste Programmierung  
 Beim robusten Dateiiterationscode müssen viele komplexe Zusammenhänge des Dateisystems berücksichtigt werden.  Weitere Informationen finden Sie in der [NTFS Technical Reference](http://go.microsoft.com/fwlink/?LinkId=79488).  
  
## Siehe auch  
 <xref:System.IO>   
 [LINQ and File Directories](../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)   
 [Das Dateisystem und die Registrierung](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)