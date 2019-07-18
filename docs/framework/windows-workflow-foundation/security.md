---
title: Sicherheit
ms.date: 03/30/2017
ms.assetid: 737ec121-bfc5-4b75-a504-2d53c2c8af39
ms.openlocfilehash: cbfb82c2db329725d3445e1a88b54e01d5813f36
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2019
ms.locfileid: "67348404"
---
# <a name="security"></a>Sicherheit
Der SQL-Workflowinstanzspeicher verwendet die folgenden Datenbanksicherheitsrollen, um den Zugriff auf Instanzstatusinformationen in der Persistenzdatenbank zu sichern.  
  
- **System.Activities.DurableInstancing.InstanceStoreUsers**. Diese Rolle verfügt über Lese- und Schreibzugriff auf öffentliche Ansichten und Ausführungsrechte auf gespeicherte Prozeduren, die zum Erstellen, Laden und Speichern von Instanzen verwendet werden.  
  
- **System.Activities.DurableInstancing.InstanceStoreObservers**. Diese Rolle verfügt über schreibgeschützten Zugriff auf öffentliche Ansichten.  
  
- **System.Activities.DurableInstancing.WorkflowActivationUsers**. Diese Rolle verfügt über die Berechtigung, gespeicherte Prozeduren auszuführen, die am Instanzaktivierungsvorgang beteiligt sind. Weitere Informationen zur instanzaktivierung finden Sie unter [Instanzaktivierung](instance-activation.md). Das Benutzerkonto, unter dem ein generischer Host (z. B. der Workflowverwaltungsdienst hosting Features von Windows Server AppFabric) ausgeführt wird, sollte dieser Datenbankrolle hinzugefügt werden.  
  
 Weitere Informationen zur Sicherheit für Persistenzspeicher mit Windows Server AppFabric finden Sie unter [Sicherheitskonfiguration für Persistenzspeicher in AppFabric](https://go.microsoft.com/fwlink/?LinkId=201208)  
  
> [!CAUTION]
>  Ein Client, der Zugriff auf seine eigenen Instanzdaten im Instanzspeicher hat, kann auch auf alle anderen Instanzen im selben Instanzspeicher zugreifen. Der Instanzspeicher unterstützt die Angabe von Sicherheitsberechtigungen auf Instanzebene nicht. Sie sollten separate Instanzspeicher erstellen und verschiedene Gruppen/Benutzer zuordnen, um auf andere Speicher zugreifen zu können.
