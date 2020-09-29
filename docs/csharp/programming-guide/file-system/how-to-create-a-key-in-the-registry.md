---
title: 'Vorgehensweise: Erstellen eines Schlüssels in der Registrierung (C#- Programmierleitfaden)'
description: Erfahren Sie, wie Sie einen Schlüssel in der Registrierung erstellen. Hier finden Sie ein Codebeispiel, Anweisungen zur Kompilierung und zusätzliche verfügbare Ressourcen.
ms.date: 07/20/2015
helpviewer_keywords:
- registry, adding keys and values [C#]
- registry keys, creating [C#]
- keys, creating in registry
ms.assetid: 8fa475b0-e01f-483a-9327-fd03488fdf5d
ms.openlocfilehash: c51fa61aa4c501921d5c7ace99a8c5aaf7b29f58
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203916"
---
# <a name="how-to-create-a-key-in-the-registry-c-programming-guide"></a>Vorgehensweise: Erstellen eines Schlüssels in der Registrierung (C#- Programmierleitfaden)

Dieses Beispiel fügt der Registrierung des aktuellen Benutzers unter dem Schlüssel "Names" das Wertepaar "Name" und "Isabella" hinzu.  
  
## <a name="example"></a>Beispiel  
  
```csharp  
Microsoft.Win32.RegistryKey key;  
key = Microsoft.Win32.Registry.CurrentUser.CreateSubKey("Names");  
key.SetValue("Name", "Isabella");  
key.Close();  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
- Kopieren Sie den Code, und fügen Sie ihn in die `Main`-Methode einer Konsolenanwendung ein.  
  
- Ersetzen Sie den `Names`-Parameter durch den Namen eines Schlüssels, der sich in der Registrierung direkt unter dem HKEY_CURRENT_USER-Knoten befindet.  
  
- Ersetzen Sie den `Name`-Parameter durch den Namen eines Werts, der sich direkt unterhalb des Names-Knotens befindet.  
  
## <a name="robust-programming"></a>Stabile Programmierung  

 Untersuchen Sie die Registrierungsstruktur, um eine adäquate Position für den Schlüssel zu ermitteln. Sie können beispielsweise den Schlüssel Software des aktuellen Benutzers öffnen und einen Schlüssel mit dem Namen Ihres Unternehmens erstellen. Anschließend fügen Sie die Registrierungswerte dem Schlüssel für das Unternehmen hinzu.  
  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
- Der Name des Schlüssels ist NULL.  
  
- Der Benutzer ist nicht zum Erstellen von Registrierungsschlüsseln berechtigt.  
  
- Der Name des Schlüssels ist länger als 255 Zeichen.  
  
- Der Schlüssel ist geschlossen.  
  
- Der Registrierungsschlüssel ist schreibgeschützt.  
  
## <a name="net-security"></a>.NET-Sicherheit  

 Es ist sicherer, die Daten in den Benutzerordner (`Microsoft.Win32.Registry.CurrentUser`) anstatt auf den lokalen Computer (`Microsoft.Win32.Registry.LocalMachine`) zu schreiben.  
  
 Wenn Sie einen Registrierungswert erstellen, müssen Sie festlegen, was geschehen soll, wenn der Wert bereits vorhanden ist. Möglicherweise wurde der Wert bereits von einem bösartigen Prozess erstellt, der nun darauf zugreifen kann. Wenn Sie dem Registrierungswert Daten hinzufügen, kann der andere Prozess darauf zugreifen. Um dies zu verhindern, verwenden Sie die `Overload:Microsoft.Win32.RegistryKey.GetValue`- -Methode. Die Methode gibt NULL zurück, wenn der Schlüssel noch nicht vorhanden ist.  
  
 Es ist nicht sicher, geheime Daten wie Kennwörter in der Registrierung als Klartext zu speichern. Dies gilt auch, wenn der Registrierungsschlüssel durch Zugriffssteuerungslisten (ACLs) geschützt ist.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IO?displayProperty=nameWithType>
- [C#-Programmierhandbuch](../index.md)
- [Das Dateisystem und die Registrierung (C#-Programmierhandbuch)](./index.md)
- [Read, write and delete from the registry with C# (Ausführen von Aktionen in der Registrierung mit C#: Lesen, Schreiben und Löschen)](https://www.codeproject.com/Articles/3389/Read-write-and-delete-from-registry-with-C)
