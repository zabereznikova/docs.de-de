---
title: Sicherheit
ms.date: 03/30/2017
ms.assetid: 737ec121-bfc5-4b75-a504-2d53c2c8af39
ms.openlocfilehash: e4419a7a73015541e0a75b4f8c615485c5fdac1b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267272"
---
# <a name="security"></a>Sicherheit

Der SQL-Workflowinstanzspeicher verwendet die folgenden Datenbanksicherheitsrollen, um den Zugriff auf Instanzstatusinformationen in der Persistenzdatenbank zu sichern.  
  
- **System. Activities. DurableInstancing. instancestoreusers**. Diese Rolle verfügt über Lese- und Schreibzugriff auf öffentliche Ansichten und Ausführungsrechte auf gespeicherte Prozeduren, die zum Erstellen, Laden und Speichern von Instanzen verwendet werden.  
  
- **System. Activities. DurableInstancing. instancestoreobserver**. Diese Rolle verfügt über schreibgeschützten Zugriff auf öffentliche Ansichten.  
  
- **System. Activities. DurableInstancing. workflowactivationusers**. Diese Rolle verfügt über die Berechtigung, gespeicherte Prozeduren auszuführen, die am Instanzaktivierungsvorgang beteiligt sind. Weitere Informationen zur instanzaktivierung finden Sie unter [instanzaktivierung](instance-activation.md). Das Benutzerkonto, unter dem ein generischer Host (z. b. der Workflow Verwaltungsdienst der Hostingfeatures von Windows Server AppFabric) ausgeführt wird, sollte dieser Daten Bank Rolle hinzugefügt werden.  
  
 Weitere Informationen zur Sicherheit für Persistenzspeicher mit Windows Server AppFabric finden Sie unter [Sicherheitskonfiguration für Persistenz-Speicher in App-Fabric](/previous-versions/appfabric/ff431727(v=azure.10)) .  
  
> [!CAUTION]
> Ein Client, der Zugriff auf seine eigenen Instanzdaten im Instanzspeicher hat, kann auch auf alle anderen Instanzen im selben Instanzspeicher zugreifen. Der Instanzspeicher unterstützt die Angabe von Sicherheitsberechtigungen auf Instanzebene nicht. Sie sollten separate Instanzspeicher erstellen und verschiedene Gruppen/Benutzer zuordnen, um auf andere Speicher zugreifen zu können.
