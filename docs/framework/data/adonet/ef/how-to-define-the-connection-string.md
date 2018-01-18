---
title: 'Gewusst wie: Definieren der Verbindungszeichenfolge'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c7c17029dade53c724420fa5604ba3448ce6a6ab
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-define-the-connection-string"></a>Gewusst wie: Definieren der Verbindungszeichenfolge
In diesem Thema ist dargestellt, wie die Verbindungszeichenfolge für die Verbindung mit einem konzeptionellen Modell definiert wird. In diesem Thema beruht auf dem [AdventureWorks Sales](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) konzeptionellen Modell. Das AdventureWorks Sales-Modell wird in den aufgabenbezogenen Themen der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]-Dokumentation verwendet. In diesem Thema wird davon ausgegangen, dass Sie bereits konfiguriert haben die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] und das AdventureWorks Sales-Modell definiert. Weitere Informationen finden Sie unter [Vorgehensweise: Manuelles Definieren der Modell- und Zuordnen von Dateien](http://msdn.microsoft.com/en-us/d4fd6864-f2a1-48f0-aa32-1e318775a99a). Die Verfahren in diesem Thema sind automatisch Mitglieder [Vorgehensweise: Manuelles Konfigurieren eines Entity Framework-Projekts](http://msdn.microsoft.com/en-us/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e).  
  
> [!NOTE]
>  Wenn Sie den [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)]-Assistenten in einem [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)]-Projekt verwenden, wird automatisch eine EDMX-Datei erstellt und das Projekt für die Verwendung von [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] konfiguriert. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden des Entity Data Model-Assistenten](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d)  
  
### <a name="to-define-the-entity-framework-connection-string"></a>So definieren Sie die Verbindungszeichenfolge für Entity Framework  
  
-   Öffnen Sie die Anwendungskonfigurationsdatei des Projekts (app.config), und fügen Sie folgende Verbindungszeichenfolge hinzu:  
  
  
  
     Wenn das Projekt nicht mit eine Anwendungskonfigurationsdatei verfügt, können Sie dazu hinzufügen **neues Element hinzufügen** aus der **Projekt** im Menü auswählen der **allgemeine** Kategorie Auswählen von **Anwendungskonfigurationsdatei**, und klicken Sie dann auf **hinzufügen**.  
  
## <a name="see-also"></a>Siehe auch  
 [Schnellstart](http://msdn.microsoft.com/en-us/0bc534be-789f-4819-b9f6-76e51d961675)  
 [Vorgehensweise: Erstellen Sie eine neue EDMX-Datei](http://msdn.microsoft.com/en-us/beb8189e-e51c-4051-839c-9902c224abf2)  
 [ADO.NET Entity Data Model Tools (ADO.NET Entity Data Model-Tools)](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)
