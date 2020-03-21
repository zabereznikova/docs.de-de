---
title: 'Gewusst wie: Definieren der Verbindungszeichenfolge'
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: e5b675a50f883825cce97275048447b79b64cc97
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150570"
---
# <a name="how-to-define-the-connection-string"></a>Gewusst wie: Definieren der Verbindungszeichenfolge

In diesem Thema ist dargestellt, wie die Verbindungszeichenfolge für die Verbindung mit einem konzeptionellen Modell definiert wird. Dieses Thema basiert auf dem konzeptuellen [AdventureWorks](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) Sales-Modell. Das "AdventureWorks Sales"-Modell wird in den aufgabenbezogenen Themen der Entity Framework-Dokumentation verwendet. In diesem Thema wird davon ausgegangen, dass Sie das Entity Framework bereits konfiguriert und das AdventureWorks-Verkaufsmodell definiert haben. Weitere Informationen finden Sie unter [Gewusst wie: Manuelle Definition des Modells und der Zuordnungsdateien](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100)). Die Verfahren in diesem Thema sind auch in Gewusst wie [folgt: Manuell konfigurieren eines Entity Framework-Projekts](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))enthalten.

> [!NOTE]
> Wenn Sie den Entitätsdatenmodell-Assistenten in einem Visual Studio-Projekt verwenden, wird automatisch eine .edmx-Datei generiert und das Projekt für die Verwendung des Entity Framework konfiguriert. Weitere Informationen finden Sie unter [Gewusst wie: Verwenden des Entitätsdatenmodell-Assistenten](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).

## <a name="to-define-the-entity-framework-connection-string"></a>So definieren Sie die Verbindungszeichenfolge für Entity Framework

- Öffnen Sie die Anwendungskonfigurationsdatei des Projekts (app.config), und fügen Sie folgende Verbindungszeichenfolge hinzu:

```xml
<connectionStrings>
    <add name="AdventureWorksEntities"
         connectionString="metadata=.\AdventureWorks.csdl|.\AdventureWorks.ssdl|.\AdventureWorks.msl;
         provider=System.Data.SqlClient;provider connection string='Data Source=localhost;
         Initial Catalog=AdventureWorks;Integrated Security=True;Connection Timeout=60;
         multipleactiveresultsets=true'" providerName="System.Data.EntityClient" />
</connectionStrings>
```

Wenn Ihr Projekt keine Anwendungskonfigurationsdatei enthält, können Sie eine hinzufügen, indem Sie im Menü **Projekt** die Option **"Neues Element hinzufügen"** auswählen, die Kategorie **Allgemein** auswählen, **die Anwendungskonfigurationsdatei**auswählen und dann auf **Hinzufügen**klicken.

## <a name="see-also"></a>Weitere Informationen

- [Quickstart](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))
- [Gewusst wie: Erstellen einer neuen EDMX-Datei](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))
- [ADO.NET Entity Data Model Tools (ADO.NET Entity Data Model-Tools)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
