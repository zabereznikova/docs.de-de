---
title: "Vorgehensweise: Lesen eines Werts aus einem Registrierungsschlüssel in Visual Basic | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- registry keys, determining if a value exists in
- My.Computer.Registry object, examples
- registry, determining if values exist
- registry keys, reading from
- registry, reading
ms.assetid: 775d0a57-68c9-464e-8949-9a39bd29cc64
caps.latest.revision: 31
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b5054e277895d185ab8ec6f6a2950d5dedbef390
ms.contentlocale: de-de
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-read-a-value-from-a-registry-key-in-visual-basic"></a>Gewusst wie: Lesen eines Werts aus einem Registrierungsschlüssel in Visual Basic
Die `GetValue`-Methode des `My.Computer.Registry`-Objekts kann verwendet werden, um Werte in der Windows-Registrierung zu lesen.  
  
 Wenn der Schlüssel („Software\MyApp“ im folgenden Beispiel) nicht vorhanden ist, wird eine Ausnahme ausgelöst. Wenn der `ValueName` („Name“ im folgenden Beispiel) nicht vorhanden ist, wird `Nothing` zurückgegeben.  
  
 Die `GetValue`-Methode kann auch verwendet werden, um zu bestimmen, ob ein bestimmter Wert in einem bestimmten Registrierungsschlüssel vorhanden ist.  
  
 Wenn Code aus einer Webanwendung die Registrierung liest, wird der aktuelle Benutzer durch die Authentifizierung und den Identitätswechsel bestimmt, die in der Webanwendung implementiert sind.  
  
### <a name="to-read-a-value-from-a-registry-key"></a>Lesen eines Werts aus einem Registrierungsschlüssel  
  
-   Verwenden Sie die `GetValue`-Methode, und geben Sie den Pfad und Namen an, um einen Wert aus dem Registrierungsschlüssel zu lesen. Das folgende Beispiel liest den Wert `Name` aus `HKEY_CURRENT_USER\Software\MyApp` und zeigt ihn in einem Nachrichtenfeld an.  
  
     [!code-vb[VbResourceTasks#4](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-read-a-value-from-a-registry-key_1.vb)]  
  
 Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar. Er befindet sich in der Codeausschnittauswahl unter **Windows Betriebssystem > Registrierung**. Weitere Informationen finden Sie unter [Codeausschnitte](https://docs.microsoft.com/visualstudio/ide/code-snippets).  
  
### <a name="to-determine-whether-a-value-exists-in-a-registry-key"></a>Bestimmen, ob ein Wert in einem Registrierungsschlüssel vorhanden ist  
  
-   Verwenden Sie die `GetValue`-Methode, um den Wert abzurufen. Der folgende Code überprüft, ob der Wert vorhanden ist, und gibt eine Meldung zurück, wenn dies nicht der Fall ist.  
  
     [!code-vb[VbResourceTasks#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-read-a-value-from-a-registry-key_2.vb)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die Registrierung enthält Schlüssel der obersten Ebene oder Stammschlüssel, die zum Speichern von Daten verwendet werden. Beispielsweise wird der HKEY_LOCAL_MACHINE-Stammschlüssel zum Speichern von Einstellungen auf Computerebene genutzt, die von allen Benutzern verwendet werden, während HKEY_CURRENT_USER zum Speichern von Daten genutzt wird, die spezifisch für einen einzelnen Benutzer sind.  
  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Der Name des Schlüssels lautet `Nothing` (<xref:System.ArgumentNullException>).  
  
-   Der Benutzer ist zum Lesen von Registrierungsschlüsseln nicht berechtigt (<xref:System.Security.SecurityException>).  
  
-   Der Name des Schlüssels überschreitet das Limit von 255 Zeichen (<xref:System.ArgumentException>).  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Die Assembly benötigt zum Ausführen dieses Prozesses eine von der <xref:System.Security.Permissions.RegistryPermission>-Klasse gewährte Berechtigungsebene. Wenn Sie in einem teilweise vertrauenswürdigen Kontext arbeiten, kann der Vorgang möglicherweise aufgrund fehlender Berechtigungen eine Ausnahme auslösen. Ebenso muss der Benutzer die richtigen Zugriffssteuerungslisten zum Erstellen von oder Schreiben auf Einstellungen verfügen. Beispielsweise besitzt eine lokale Anwendung, die die Sicherheitsberechtigung für den Codezugriff besitzt, möglicherweise keine Betriebssystemberechtigung. Weitere Informationen finden Sie unter [Grundlagen der Codezugriffssicherheit](https://msdn.microsoft.com/library/33tceax8).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>   
 <xref:Microsoft.Win32.RegistryHive>   
 [Lesen aus der und Schreiben in die Registrierung](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
