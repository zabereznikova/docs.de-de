---
title: 'In die Ausgabedatei "<filename>" konnte nicht geschrieben werden: <error>.'
ms.date: 07/20/2015
f1_keywords:
- vbc31019
- bc31019
helpviewer_keywords:
- BC31019
ms.assetid: 0845b245-11bb-46fd-95ca-f6cef3c318ef
ms.openlocfilehash: 73fce70c0740992e2e9159946d428d214576e163
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870291"
---
# <a name="unable-to-write-to-output-file-filename-error"></a>In die Ausgabedatei "\<filename>" konnte nicht geschrieben werden: \<error>.

Beim Erstellen der Datei ist ein Fehler aufgetreten.  
  
 Eine Ausgabedatei kann nicht zum Schreiben geöffnet werden. Die Datei (oder der Ordner, der die Datei enthält) kann für die Exklusivnutzung durch einen anderen Prozess geöffnet sein, oder sie ist schreibgeschützt.  
  
 Häufige Situationen, in denen eine Datei exklusiv genutzt wird, sind:  
  
- Die Anwendung wird bereits ausgeführt und nutzt die Dateien. Stellen Sie zum Lösen dieses Problems sicher, dass die Anwendung nicht ausgeführt wird.  
  
- Die Datei wurde in einer anderen Anwendung geöffnet. Stellen Sie zum Lösen dieses Problems sicher, dass keine andere Anwendung auf die Dateien zugreift. Es ist nicht immer ersichtlich, welche Anwendung auf Ihre Dateien zugreift; ein Neustart Ihres Computer kann in diesem Fall der einfachste Weg sein, um die Anwendung zu beenden.  
  
 Es reicht aus, dass eine Projektausgabedatei schreibgeschützt ist, um diese Ausnahme auszulösen.  
  
 **Fehler-ID:** BC31019  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Kompilieren Sie das Programm erneut, um festzustellen, ob der Fehler erneut auftritt.  
  
2. Wenn der Fehler weiterhin auftritt, speichern Sie Ihre Arbeit, und starten Sie Visual Studio neu.  
  
3. Wenn der Fehler weiterhin besteht, starten Sie den Computer neu.  
  
4. Wenn der Fehler erneut auftritt, installieren Sie Visual Basic neu.  
  
5. Wenn der Fehler auch nach der erneuten Installation auftritt, informieren Sie den Produktsupport von Microsoft.  
  
### <a name="to-check-file-attributes-in-file-explorer"></a>So prüfen Sie Dateiattribute im Datei-Explorer  
  
1. Öffnen Sie den gewünschten Ordner.  
  
2. Klicken Sie auf das Symbol **Sichten** , und wählen Sie **Details**.  
  
3. Klicken Sie mit der rechten Maustaste auf den Spaltenheader, und wählen Sie in der Dropdown Liste die Option **Attribute** aus.  
  
### <a name="to-change-the-attributes-of-a-file-or-folder"></a>So ändern Sie die Attribute einer Datei oder eines Ordners  
  
1. Klicken Sie im **Datei-Explorer**mit der rechten Maustaste auf die Datei oder den Ordner, und wählen Sie **Eigenschaften**.  
  
2. Deaktivieren **Sie** im Abschnitt **Attribute** der Registerkarte **Allgemein** das Kontrollkästchen schreibgeschützt.  
  
3. Klicken Sie auf **OK**.  
  
## <a name="see-also"></a>Weitere Informationen

- [Sprechen Sie mit uns](/visualstudio/ide/feedback-options)
