---
title: Sicherheit
ms.date: 03/30/2017
ms.assetid: 737ec121-bfc5-4b75-a504-2d53c2c8af39
ms.openlocfilehash: c27ac9cf41436332d560e11987e3ce4b68576895
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004691"
---
# <a name="security"></a>Sicherheit
Der SQL-Workflowinstanzspeicher verwendet die folgenden Datenbanksicherheitsrollen, um den Zugriff auf Instanzstatusinformationen in der Persistenzdatenbank zu sichern.  
  
- **System.Activities.DurableInstancing.InstanceStoreUsers**. Diese Rolle verfügt über Lese- und Schreibzugriff auf öffentliche Ansichten und Ausführungsrechte auf gespeicherte Prozeduren, die zum Erstellen, Laden und Speichern von Instanzen verwendet werden.  
  
- **System.Activities.DurableInstancing.InstanceStoreObservers**. Diese Rolle verfügt über schreibgeschützten Zugriff auf öffentliche Ansichten.  
  
- **System.Activities.DurableInstancing.WorkflowActivationUsers**. Diese Rolle verfügt über die Berechtigung, gespeicherte Prozeduren auszuführen, die am Instanzaktivierungsvorgang beteiligt sind. Weitere Informationen zur instanzaktivierung finden Sie unter [Instanzaktivierung](instance-activation.md). Das Benutzerkonto, unter dem ein generischer Host ausgeführt wird (z. B. der Workflowverwaltungsdienst von [!INCLUDE[dublin](../../../includes/dublin-md.md)]), sollte dieser Datenbankrolle hinzugefügt werden.  
  
 Weitere Informationen zur Sicherheit für Persistenzspeicher mit Windows Server AppFabric finden Sie unter [Sicherheitskonfiguration für Persistenzspeicher in AppFabric](https://go.microsoft.com/fwlink/?LinkId=201208)  
  
> [!CAUTION]
>  Ein Client, der Zugriff auf seine eigenen Instanzdaten im Instanzspeicher hat, kann auch auf alle anderen Instanzen im selben Instanzspeicher zugreifen. Der Instanzspeicher unterstützt die Angabe von Sicherheitsberechtigungen auf Instanzebene nicht. Sie sollten separate Instanzspeicher erstellen und verschiedene Gruppen/Benutzer zuordnen, um auf andere Speicher zugreifen zu können.
