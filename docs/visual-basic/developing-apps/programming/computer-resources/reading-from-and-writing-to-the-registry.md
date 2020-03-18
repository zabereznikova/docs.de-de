---
title: Lesen von der und Schreiben in die Registrierung
ms.date: 07/20/2015
helpviewer_keywords:
- My.Computer.Registry object, tasks
- registry [Visual Basic], writing to
- registry [Visual Basic], reading
ms.assetid: a13da106-185b-41d7-b23c-416da65e21e4
ms.openlocfilehash: 89db9ef9db4235c069d6239d32e4f8679fbabf0b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "74349764"
---
# <a name="reading-from-and-writing-to-the-registry-visual-basic"></a>Lesen aus der und Schreiben in die Registrierung (Visual Basic)

In diesem Thema werden die Aufgaben und konzeptionellen Themen beschrieben, die mit der Registrierung in Verbindung stehen.  
  
 Beim Programmieren in Visual Basic können Sie auf die Registrierung zugreifen. Dies geschieht entweder über die in Visual Basic bereitgestellten Funktionen oder die Registrierungsklassen von .NET Framework. Die Registrierung enthält Informationen des Betriebssystems und Informationen von auf dem Computer gehosteten Anwendungen. Das Arbeiten mit der Registrierung schränkt möglicherweise die Sicherheit ein, da nicht ordnungsgemäßer Zugriff auf Systemressourcen oder geschützte Informationen zugelassen wird.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [Gewusst wie: Erstellen von Registrierungsschlüsseln und Festlegen ihrer Werte](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-create-a-registry-key-and-set-its-value.md)  
 Beschreibt die Verwendung der Methoden `CreateSubKey` und `SetValue` des `My.Computer.Registry`-Objekts zum Erstellen eines Registrierungsschlüssels und das Festlegen seines Werts  
  
 [Gewusst wie: Lesen eines Werts aus einem Registrierungsschlüssel](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-read-a-value-from-a-registry-key.md)  
 Beschreibt die Verwendung der `GetValue`-Methode des `My.Computer.Registry`-Objekts zum Lesen eines Werts aus einem Registrierungsschlüssel  
  
 [Gewusst wie: Löschen von Registrierungsschlüsseln](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-delete-a-registry-key.md)  
 Beschreibt die Verwendung der `DeleteSubKey`-Methode der `My.Computer.Registry.CurrentUser`-Eigenschaft zum Löschen eines Registrierungsschlüssels  
  
 [Lesen aus der und Schreiben in die Registrierung mithilfe des Namespaces „Microsoft.Win32“](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry-using-the-microsoft-win32-namespace.md)  
 Beschreibt die Verwendung der Klassen `Registry` und `RegistryKey` von .NET Framework für den Zugriff auf die Registrierung  
  
 [Sicherheit und die Registrierung](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)  
 Beschreibt Sicherheitsprobleme im Zusammenhang mit der Registrierung  
  
## <a name="related-sections"></a>Verwandte Abschnitte  

 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>  
 Listet die Member des `My.Computer.Registry`-Objekts auf und erklärt diese  
  
 <xref:Microsoft.Win32.Registry>  
 Bietet einen Überblick über die Klasse `Registry` und Links zu einzelnen Schlüsseln und Membern
