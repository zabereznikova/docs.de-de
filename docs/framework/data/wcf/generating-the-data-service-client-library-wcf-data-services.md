---
title: Generieren der Datendienst-Clientbibliothek (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- Add Service Reference dialog box
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
ms.openlocfilehash: 41f4e7cd633cf6175b6b167937cf53ceb4d9ec59
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2019
ms.locfileid: "56092097"
---
# <a name="generating-the-data-service-client-library-wcf-data-services"></a>Generieren der Datendienst-Clientbibliothek (WCF Data Services)
Ein Datendienst, die implementiert die [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] kann ein dienstmetadatendokument an, die von verfügbar gemachten Datenmodell beschreibt Zurückgeben der [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed. Weitere Informationen finden Sie unter [OData: Service Metadatendokument](https://go.microsoft.com/fwlink/?LinkId=186070). Können Sie die **Hinzufügen eines Dienstverweises** Dialogfeld in Visual Studio zum Hinzufügen eines Verweises auf ein [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-basierten Dienst. Wenn Sie dieses Tool verwenden, um einen Verweis auf das vom zurückgegebenen Metadaten Hinzufügen einer [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed in einem Clientprojekt die folgenden Aktionen ausgeführt:  
  
-   Fordert das Dienstmetadatendokument vom Datendienst an und interpretiert die zurückgegebenen Metadaten.  
  
    > [!NOTE]
    >  Die zurückgegebenen Metadaten werden im Clientprojekt als EDMX-Datei gespeichert. Diese EDMX-Datei kann nicht mit dem Entity Data Model-Designer geöffnet werden, da sie nicht das gleiche Format wie eine vom Entity Framework verwendete EDMX-Datei aufweist. Sie können diese Metadatendatei mit dem XML-Editor oder einem beliebigen Texteditor anzeigen. Weitere Informationen finden Sie unter den [ \[MC-EDMX\]: Entity Data Model für Data Services Packaging Format](https://go.microsoft.com/fwlink/?LinkID=178833) Spezifikation  
  
-   Generiert eine Darstellung des Diensts als Entitätscontainerklasse, die vom <xref:System.Data.Services.Client.DataServiceContext> erbt. Diese generierte Entitätscontainerklasse entspricht dem Entitätscontainer, den die Entity Data Model-Tools generieren. Weitere Informationen finden Sie unter [Übersicht über Object Services (Entity Framework)](https://docs.microsoft.com/previous-versions/bb386871(v=vs.100)).  
  
-   Generiert Datenklassen für die in den Dienstmetadaten erkannten Datenmodelltypen.  
  
-   Fügt dem Projekt einen Verweis auf die `System.Data.Services.Client`-Assembly hinzu.  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen ein Datendienstverweises](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).  
  
 Die Client-Datendienstklassen können auch generiert werden, mithilfe der [DataSvcUtil.exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) Tool an der Eingabeaufforderung. Weitere Informationen finden Sie unter [Vorgehensweise: Manuelles Generieren von Clientdatendienstklassen](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).  
  
## <a name="client-data-type-mapping"></a>Zuordnung von Clientdatentypen  
 Bei Verwendung der **Hinzufügen eines Dienstverweises** Dialogfeld in Visual Studio oder die `DataSvcUtil.exe` clientdatenklassen generieren auf der Grundlage von eine [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed, den primitiven Typen von der .NET Framework-Datentypen zugeordnet sind die Datenmodell wie folgt:  
  
|Datenmodelltyp|.NET Framework-Datentyp|  
|---------------------|------------------------------|  
|`Edm.Binary`|<xref:System.Byte> `[]`|  
|`Edm.Boolean`|<xref:System.Boolean>|  
|`Edm.Byte`|<xref:System.Byte>|  
|`Edm.DateTime`|<xref:System.DateTime>|  
|`Edm.Decimal`|<xref:System.Decimal>|  
|`Edm.Double`|<xref:System.Double>|  
|`Edm.Guid`|<xref:System.Guid>|  
|`Edm.Int16`|<xref:System.Int16>|  
|`Edm.Int32`|<xref:System.Int32>|  
|`Edm.Int64`|<xref:System.Int64>|  
|`Edm.SByte`|<xref:System.SByte>|  
|`Edm.Single`|<xref:System.Single>|  
|`Edm.String`|<xref:System.String>|  
  
 Weitere Informationen finden Sie unter [OData: Primitive Datentypen](https://go.microsoft.com/fwlink/?LinkId=186072).  
  
## <a name="see-also"></a>Siehe auch
- [WCF Data Services-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
- [Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
