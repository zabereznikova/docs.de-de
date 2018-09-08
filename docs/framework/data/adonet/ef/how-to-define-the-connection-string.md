---
title: 'Gewusst wie: Definieren der Verbindungszeichenfolge'
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: f40b8bc68eda1cb4b64b34d12b2922da69929203
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44210161"
---
# <a name="how-to-define-the-connection-string"></a>Gewusst wie: Definieren der Verbindungszeichenfolge
In diesem Thema ist dargestellt, wie die Verbindungszeichenfolge für die Verbindung mit einem konzeptionellen Modell definiert wird. In diesem Thema basiert auf der [AdventureWorks Sales](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) konzeptionellen Modell. Das AdventureWorks Sales-Modell wird in den aufgabenbezogenen Themen der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]-Dokumentation verwendet. In diesem Thema wird davon ausgegangen, dass Sie bereits konfiguriert haben die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] und definiert das AdventureWorks Sales-Modell. Weitere Informationen finden Sie unter [Vorgehensweise: Manuelles Definieren der Modell- und Mapping-Dateien](https://msdn.microsoft.com/library/d4fd6864-f2a1-48f0-aa32-1e318775a99a). Die Verfahren in diesem Thema sind auch in enthalten [Vorgehensweise: Manuelles Konfigurieren eines Entity Framework-Projekts](https://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e).  
  
> [!NOTE]
>  Bei Verwendung der [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] Assistenten in einem Visual Studio-Projekt wird automatisch eine EDMX-Datei generiert und konfiguriert das Projekt für die Verwendung der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden des Assistenten für Entity Data Model](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d)  
  
### <a name="to-define-the-entity-framework-connection-string"></a>So definieren Sie die Verbindungszeichenfolge für Entity Framework  
  
-   Öffnen Sie die Anwendungskonfigurationsdatei des Projekts (app.config), und fügen Sie folgende Verbindungszeichenfolge hinzu:  
  
  
  
     Wenn Ihr Projekt keine Konfigurationsdatei einer Anwendung vorhanden ist, können Sie hinzufügen, dazu **neues Element hinzufügen** aus der **Projekt** im Menü auswählen der **allgemeine** Kategorie Auswählen von **Anwendungskonfigurationsdatei**, und klicken Sie dann auf **hinzufügen**.  
  
## <a name="see-also"></a>Siehe auch  
 [Schnellstart](https://msdn.microsoft.com/library/0bc534be-789f-4819-b9f6-76e51d961675)  
 [Vorgehensweise: Erstellen einer neuen EDMX-Datei](https://msdn.microsoft.com/library/beb8189e-e51c-4051-839c-9902c224abf2)  
 [ADO.NET Entity Data Model Tools (ADO.NET Entity Data Model-Tools)](https://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)
