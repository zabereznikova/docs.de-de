---
title: Sicherheit
ms.date: 03/30/2017
ms.assetid: 737ec121-bfc5-4b75-a504-2d53c2c8af39
ms.openlocfilehash: 0fd77ce335848c58a7b734236124b90999355270
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837674"
---
# <a name="security"></a>Sicherheit
Der SQL-Workflowinstanzspeicher verwendet die folgenden Datenbanksicherheitsrollen, um den Zugriff auf Instanzstatusinformationen in der Persistenzdatenbank zu sichern.  
  
- **System.Activities.DurableInstancing.InstanceStoreUsers**. Diese Rolle verfügt über Lese- und Schreibzugriff auf öffentliche Ansichten und Ausführungsrechte auf gespeicherte Prozeduren, die zum Erstellen, Laden und Speichern von Instanzen verwendet werden.  
  
- **System.Activities.DurableInstancing.InstanceStoreObservers**. Diese Rolle verfügt über schreibgeschützten Zugriff auf öffentliche Ansichten.  
  
- **System.Activities.DurableInstancing.WorkflowActivationUsers**. Diese Rolle verfügt über die Berechtigung, gespeicherte Prozeduren auszuführen, die am Instanzaktivierungsvorgang beteiligt sind. Weitere Informationen zur instanzaktivierung finden Sie unter [instanzaktivierung](instance-activation.md). Das Benutzerkonto, unter dem ein generischer Host (z. b. der Workflow Verwaltungsdienst der Hostingfeatures von Windows Server AppFabric) ausgeführt wird, sollte dieser Daten Bank Rolle hinzugefügt werden.  
  
 Weitere Informationen zur Sicherheit für Persistenzspeicher mit Windows Server AppFabric finden Sie unter [Sicherheitskonfiguration für Persistenz-Speicher in App-Fabric](https://docs.microsoft.com/previous-versions/appfabric/ff431727(v=azure.10)) .  
  
> [!CAUTION]
> Ein Client, der Zugriff auf seine eigenen Instanzdaten im Instanzspeicher hat, kann auch auf alle anderen Instanzen im selben Instanzspeicher zugreifen. Der Instanzspeicher unterstützt die Angabe von Sicherheitsberechtigungen auf Instanzebene nicht. Sie sollten separate Instanzspeicher erstellen und verschiedene Gruppen/Benutzer zuordnen, um auf andere Speicher zugreifen zu können.
