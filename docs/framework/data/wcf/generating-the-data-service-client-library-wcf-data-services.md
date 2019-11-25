---
title: Generieren der Datendienst-Clientbibliothek (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- Add Service Reference dialog box
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
ms.openlocfilehash: f73ea93fe76f31c81935dbfb29183c247e41d8cd
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975282"
---
# <a name="generating-the-data-service-client-library-wcf-data-services"></a>Generieren der Datendienst-Clientbibliothek (WCF Data Services)
Ein Datendienst, der die Open Data Protocol (odata) implementiert, kann ein dienstmetadatendokument zurückgeben, das das Datenmodell beschreibt, das vom odata-Feed verfügbar gemacht wird. Weitere Informationen finden Sie unter [odata: dienstmetadatendokument](https://go.microsoft.com/fwlink/?LinkId=186070). Sie können das Dialogfeld " **Dienstverweis hinzufügen** " in Visual Studio verwenden, um einen Verweis auf einen odata-basierten Dienst hinzuzufügen. Wenn Sie dieses Tool verwenden, um einen Verweis auf die von einem odata-Feed in einem Client Projekt zurückgegebenen Metadaten hinzuzufügen, führt es die folgenden Aktionen aus:  
  
- Fordert das Dienstmetadatendokument vom Datendienst an und interpretiert die zurückgegebenen Metadaten.  
  
    > [!NOTE]
    > Die zurückgegebenen Metadaten werden im Clientprojekt als EDMX-Datei gespeichert. Diese EDMX-Datei kann nicht mit dem Entity Data Model-Designer geöffnet werden, da sie nicht das gleiche Format wie eine vom Entity Framework verwendete EDMX-Datei aufweist. Sie können diese Metadatendatei mit dem XML-Editor oder einem beliebigen Texteditor anzeigen. Weitere Informationen finden Sie in der Spezifikation [\[MC-edmx\]: Entity Data Model for Data Services Packaging Format](https://go.microsoft.com/fwlink/?LinkID=178833) .  
  
- Generiert eine Darstellung des Diensts als Entitätscontainerklasse, die vom <xref:System.Data.Services.Client.DataServiceContext> erbt. Diese generierte Entitätscontainerklasse entspricht dem Entitätscontainer, den die Entity Data Model-Tools generieren. Weitere Informationen finden Sie unter [Übersicht über Object Services (Entity Framework)](https://docs.microsoft.com/previous-versions/bb386871(v=vs.100)).  
  
- Generiert Datenklassen für die in den Dienstmetadaten erkannten Datenmodelltypen.  
  
- Fügt dem Projekt einen Verweis auf die `System.Data.Services.Client`-Assembly hinzu.  
  
 Weitere Informationen finden Sie unter Vorgehens [Weise: Hinzufügen eines Datendienst Verweises](how-to-add-a-data-service-reference-wcf-data-services.md).  
  
 Die Client Datendienst Klassen können auch mit dem Tool [DataSvcUtil. exe](wcf-data-service-client-utility-datasvcutil-exe.md) an der Eingabeaufforderung generiert werden. Weitere Informationen finden Sie unter Gewusst [wie: Manuelles Generieren von Client Datendienst Klassen](how-to-manually-generate-client-data-service-classes-wcf-data-services.md).  
  
## <a name="client-data-type-mapping"></a>Zuordnung von Clientdatentypen  
 Wenn Sie das Dialogfeld " **Dienstverweis hinzufügen** " in Visual Studio oder das `DataSvcUtil.exe`-Tool verwenden, um Client Daten Klassen zu generieren, die auf einem odata-Feed basieren, werden die .NET Framework-Datentypen wie folgt den primitiven Typen aus dem Datenmodell zugeordnet:  
  
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
  
 Weitere Informationen finden Sie unter [odata: primitive Datentypen](https://go.microsoft.com/fwlink/?LinkId=186072).  
  
## <a name="see-also"></a>Siehe auch

- [WCF Data Services-Clientbibliothek](wcf-data-services-client-library.md)
- [Schnellstart](quickstart-wcf-data-services.md)
