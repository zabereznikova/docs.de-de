---
title: 'Vorgehensweise: Definieren der Verbindungszeichenfolge'
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: 9ce0b427cac17fc338877c5f85d3648d15d5ee14
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833950"
---
# <a name="how-to-define-the-connection-string"></a>Vorgehensweise: Definieren der Verbindungszeichenfolge

In diesem Thema ist dargestellt, wie die Verbindungszeichenfolge für die Verbindung mit einem konzeptionellen Modell definiert wird. Dieses Thema basiert auf dem konzeptionellen [AdventureWorks Sales](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) -Modell. Das "AdventureWorks Sales"-Modell wird in den aufgabenbezogenen Themen der Entity Framework-Dokumentation verwendet. In diesem Thema wird davon ausgegangen, dass Sie die Entity Framework bereits konfiguriert und das AdventureWorks Sales-Modell definiert haben. Weitere Informationen finden Sie unter [Vorgehensweise: Manuelles Definieren der Modell-und](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100))Mapping-Dateien. Die Verfahren in diesem Thema sind auch in [Gewusst wie: Manuelles Konfigurieren eines Entity Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))Projekts.

> [!NOTE]
> Wenn Sie den Entity Data Model-Assistenten in einem Visual Studio-Projekt verwenden, wird automatisch eine EDMX-Datei generiert, und das Projekt wird so konfiguriert, dass die Entity Framework verwendet wird. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden Sie den Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))-Assistenten.

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

Wenn für das Projekt keine Anwendungs Konfigurationsdatei vorhanden ist, können Sie eines hinzufügen, indem Sie im Menü **Projekt** die Option **Neues Element hinzufügen** auswählen, die Kategorie **Allgemein** auswählen, **Anwendungs Konfigurationsdatei**auswählen und dann auf **Fügen Sie hinzu**.

## <a name="see-also"></a>Siehe auch

- [Schnellstart](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))
- [Vorgehensweise: Erstellen einer neuen EDMX-Datei](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))
- [ADO.NET Entity Data Model Tools (ADO.NET Entity Data Model-Tools)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
