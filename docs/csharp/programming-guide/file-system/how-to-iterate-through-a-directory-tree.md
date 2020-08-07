---
title: 'Vorgehensweise: Durchlaufen einer Verzeichnisstruktur (C#-Programmierleitfaden)'
description: Erfahren Sie, wie Sie eine Verzeichnisstruktur durchlaufen. Greifen Sie auf jede Datei in jedem geschachtelten Unterverzeichnis unterhalb eines angegebenen Stammordners zu.
ms.date: 07/20/2015
helpviewer_keywords:
- iterating through folders [C#]
- file iteration [C#]
ms.assetid: c4be4a75-6b1b-46a7-9d38-bab353091ed7
ms.openlocfilehash: c49a9d1eaea9d4d8967b105d753f2a611d80e795
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301982"
---
# <a name="how-to-iterate-through-a-directory-tree-c-programming-guide"></a>Vorgehensweise: Durchlaufen einer Verzeichnisstruktur (C#-Programmierleitfaden)
Der Ausdruck „Durchlaufen einer Verzeichnisstruktur“ bedeutet, dass auf jede Datei in jedem verschachtelten Unterverzeichnis in einem angegebenen Stammordner in einer beliebigen Tiefe zugegriffen wird. Sie müssen nicht unbedingt jede Datei öffnen. Sie können einfach den Namen der Datei oder dem Unterverzeichnis als `string` abrufen, oder Sie können zusätzliche Informationen eines <xref:System.IO.FileInfo?displayProperty=nameWithType> oder <xref:System.IO.DirectoryInfo?displayProperty=nameWithType>-Objekts abrufen.  
  
> [!NOTE]
> In Windows sind die Begriffe „Verzeichnis“ und „Ordner“ austauschbar. Die meisten Dokumentationen und der Text der Benutzeroberfläche verwenden den Begriff „Ordner“, aber die .NET-Klassenbibliotheken verwenden den Begriff „Verzeichnis“.  
  
 Im einfachsten Fall, in dem Sie ganz sicher sind, dass Sie über die Zugriffsberechtigungen für alle Verzeichnisse in einem angegebenen Stamm verfügen, können Sie das `System.IO.SearchOption.AllDirectories`-Flag verwenden. Dieses Flag gibt alle geschachtelten Unterverzeichnisse zurück, die mit dem angegebenen Muster übereinstimmen. Im folgenden Beispiel wird die Verwendung dieses Flags veranschaulicht.  
  
```csharp  
root.GetDirectories("*.*", System.IO.SearchOption.AllDirectories);  
```  
  
 Der Schwachpunkt bei diesem Ansatz ist, dass die Methode fehlschlägt und keine Verzeichnisse zurückgibt, wenn eines der Unterverzeichnisse im angegebenen Stamm eine <xref:System.IO.DirectoryNotFoundException> oder <xref:System.UnauthorizedAccessException> bewirkt. Dasselbe gilt bei Verwendung der <xref:System.IO.DirectoryInfo.GetFiles%2A>-Methode. Wenn Sie diese Ausnahmen für bestimmte Unterverzeichnisse behandeln müssen, müssen Sie die Verzeichnisstruktur manuell durchlaufen, wie in den folgenden Beispielen gezeigt.  
  
 Wenn Sie eine Verzeichnisstruktur manuell durchlaufen, können Sie zuerst die Unterverzeichnisse (*Durchlauf vor der Sortierung*) oder die Dateien (*Durchlauf nach der Sortierung*) behandeln. Wenn Sie einen Durchlauf vor der Sortierung ausführen, durchlaufen Sie die gesamte Struktur unter dem aktuellen Ordner, bevor Sie die Dateien durchlaufen, die sich direkt in diesem Ordner befinden. In den Beispielen weiter unten in diesem Dokument wird ein Durchlauf nach der Sortierung ausgeführt, aber Sie können die Beispiele problemlos abändern, um einen Durchlauf vor der Sortierung auszuführen.  
  
 Eine andere Option ist, entweder Rekursion oder einen stapelbasierten Durchlauf zu verwenden. In den Beispielen weiter unten in diesem Dokument werden beide Ansätze gezeigt.  
  
 Wenn Sie mehrere Vorgänge für Dateien und Ordner ausführen müssen, können Sie diese Beispiele modularisieren, indem Sie den Vorgang in separate Funktionen umgestalten, die Sie mit einem einzelnen Delegaten aufrufen können.  
  
> [!NOTE]
> NTFS-Dateisysteme können *Analysepunkte* in Form von *Verknüpfungspunkten*, *symbolischen Verknüpfungen* und *festen Links* enthalten. .NET wie z. B. <xref:System.IO.DirectoryInfo.GetFiles%2A> und <xref:System.IO.DirectoryInfo.GetDirectories%2A> geben keine Unterverzeichnisse unter einem Analysepunkt zurück. Dieses Verhalten schützt vor dem Risiko einer Endlosschleife, wenn zwei Analysepunkte aufeinander verweisen. Im Allgemeinen sollten Sie bei Analysepunkten äußerst vorsichtig sein, um sicherzustellen, dass Sie nicht versehentlich Dateien ändern oder löschen. Wenn Sie genaue Kontrolle über Analysepunkte benötigen, verwenden Sie einen Plattformaufruf oder nativen Code, um die entsprechenden Win32-Dateisystemmethoden direkt aufzurufen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie eine Verzeichnisstruktur mit Rekursion direkt durchlaufen. Der rekursive Ansatz ist elegant, kann aber eine Stapelüberlaufausnahme verursachen, wenn die Verzeichnisstruktur groß und tief verschachtelt ist.  
  
 Die besonderen Ausnahmen, die verarbeitet werden, und die besonderen Aktionen, die für jede Datei und jeden Ordner ausgeführt werden, werden nur als Beispiele angegeben. Sie sollten diesen Code für Ihre speziellen Anforderungen ändern. Weitere Informationen finden Sie in den Kommentaren im Code.  
  
 [!code-csharp[csFilesandFolders#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#1)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie Dateien und Ordner in einer Verzeichnisstruktur ohne Rekursion durchlaufen. Diese Technik verwendet den generischen <xref:System.Collections.Generic.Stack%601>-Auflistungstyp, bei dem es sich um einen LIFO-Stapel handelt.  
  
 Die besonderen Ausnahmen, die verarbeitet werden, und die besonderen Aktionen, die für jede Datei und jeden Ordner ausgeführt werden, werden nur als Beispiele angegeben. Sie sollten diesen Code für Ihre speziellen Anforderungen ändern. Weitere Informationen finden Sie in den Kommentaren im Code.  
  
 [!code-csharp[csFilesandFolders#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#2)]  
  
 Es ist im Allgemeinen zu zeitaufwändig, bei allen Ordnern zu testen, ob die Anwendung über die Berechtigung zum Öffnen verfügt. Im Codebeispiel wird daher nur dieser Teil der Operation in einen `try/catch`-Block eingeschlossen. Sie können den `catch`-Block ändern, sodass Sie bei verweigertem Zugriff auf einen Ordner versuchen, Ihre Berechtigungen zu erhöhen, und dann erneut darauf zugreifen. In der Regel sollten Sie nur die Ausnahmen abfangen, die Sie behandeln können, ohne Ihre Anwendung in einem unbekannten Status zu lassen.  
  
 Wenn Sie den Inhalt einer Verzeichnisstruktur entweder im Arbeitsspeicher oder auf dem Datenträger speichern müssen, speichern Sie am besten nur die <xref:System.IO.FileSystemInfo.FullName%2A>-Eigenschaft (vom Typ `string`) für jede Datei. Anschließend können Sie diese Zeichenfolge nach Bedarf zum Erstellen eines neuen <xref:System.IO.FileInfo>- oder <xref:System.IO.DirectoryInfo>-Objekts verwenden, oder eine beliebige Datei öffnen, für die zusätzliche Verarbeitung erforderlich ist.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Bei stabilem Dateiiterationscode müssen viele komplexe Zusammenhänge des Dateisystems berücksichtigt werden. Weitere Informationen zum Windows-Dateisystem finden Sie in der [Übersicht zu NTFS](/windows-server/storage/file-server/ntfs-overview).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IO>
- [LINQ und Dateiverzeichnisse](../concepts/linq/linq-and-file-directories.md)
- [Das Dateisystem und die Registrierung (C#-Programmierhandbuch)](./index.md)
