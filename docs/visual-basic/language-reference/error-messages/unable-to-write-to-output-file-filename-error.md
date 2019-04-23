---
title: "In die Ausgabedatei '<filename>' konnte nicht geschrieben werden: <error>."
ms.date: 07/20/2015
f1_keywords:
- vbc31019
- bc31019
helpviewer_keywords:
- BC31019
ms.assetid: 0845b245-11bb-46fd-95ca-f6cef3c318ef
ms.openlocfilehash: f29eb628c079f65a520cf5e1ccd8afed549f7cad
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59318220"
---
# <a name="unable-to-write-to-output-file-filename-error"></a>Beim Schreiben in die Ausgabedatei kann nicht '\<Dateiname >': \<Fehler >
Beim Erstellen der Datei ist ein Fehler aufgetreten.  
  
 Eine Ausgabedatei kann nicht zum Schreiben geöffnet werden. Die Datei (oder der Ordner, der die Datei enthält) kann für die Exklusivnutzung durch einen anderen Prozess geöffnet sein, oder sie ist schreibgeschützt.  
  
 Häufige Situationen, in denen eine Datei exklusiv genutzt wird, sind:  
  
-   Die Anwendung wird bereits ausgeführt und nutzt die Dateien. Stellen Sie zum Lösen dieses Problems sicher, dass die Anwendung nicht ausgeführt wird.  
  
-   Die Datei wurde in einer anderen Anwendung geöffnet. Stellen Sie zum Lösen dieses Problems sicher, dass keine andere Anwendung auf die Dateien zugreift. Es ist nicht immer ersichtlich, welche Anwendung auf Ihre Dateien zugreift; ein Neustart Ihres Computer kann in diesem Fall der einfachste Weg sein, um die Anwendung zu beenden.  
  
 Es reicht aus, dass eine Projektausgabedatei schreibgeschützt ist, um diese Ausnahme auszulösen.  
  
 **Fehler-ID:** BC31019  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Kompilieren Sie das Programm erneut, um festzustellen, ob der Fehler erneut auftritt.  
  
2. Wenn der Fehler weiterhin auftritt, speichern Sie Ihre Arbeit, und starten Sie Visual Studio.  
  
3. Wenn der Fehler weiterhin besteht, starten Sie den Computer neu.  
  
4. Wenn der Fehler erneut auftritt, installieren Sie Visual Basic.  
  
5. Wenn der Fehler auch nach der erneuten Installation auftritt, informieren Sie den Produktsupport von Microsoft.  
  
### <a name="to-check-file-attributes-in-file-explorer"></a>So prüfen Sie Dateiattribute im Datei-Explorer  
  
1. Öffnen Sie den gewünschten Ordner.  
  
2. Klicken Sie auf die **Ansichten** Symbol, und wählen Sie **Details**.  
  
3. Mit der rechten Maustaste in der Kopfzeile der Spalte, und wählen **Attribute** aus der Dropdown-Liste.  
  
### <a name="to-change-the-attributes-of-a-file-or-folder"></a>So ändern Sie die Attribute einer Datei oder eines Ordners  
  
1. In **Datei-Explorer**mit der rechten Maustaste auf die Datei oder den Ordner, und wählen Sie **Eigenschaften**.  
  
2. In der **Attribute** Teil der **allgemeine** Registerkarte die **schreibgeschützte** Feld.  
  
3. Klicken Sie auf **OK**.  
  
## <a name="see-also"></a>Siehe auch

- [Sprechen Sie mit uns](/visualstudio/ide/talk-to-us)
