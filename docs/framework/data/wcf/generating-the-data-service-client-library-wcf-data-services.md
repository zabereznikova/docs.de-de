---
title: Generieren der Datendienst-Clientbibliothek (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- Add Service Reference dialog box
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
ms.openlocfilehash: 050a791736e90b5daf46fd272197ca21a220afb0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172618"
---
# <a name="generating-the-data-service-client-library-wcf-data-services"></a>Generieren der Datendienst-Clientbibliothek (WCF Data Services)

Ein Datendienst, der die Open Data Protocol (odata) implementiert, kann ein dienstmetadatendokument zurückgeben, das das Datenmodell beschreibt, das vom odata-Feed verfügbar gemacht wird. Weitere Informationen finden Sie im Abschnitt Dienst Metadaten-Dokument im Artikel [odata: Übersicht](https://www.odata.org/documentation/odata-version-2-0/overview/) . Sie können das Dialogfeld " **Dienstverweis hinzufügen** " in Visual Studio verwenden, um einen Verweis auf einen odata-basierten Dienst hinzuzufügen. Wenn Sie dieses Tool verwenden, um einen Verweis auf die von einem odata-Feed in einem Client Projekt zurückgegebenen Metadaten hinzuzufügen, führt es die folgenden Aktionen aus:  
  
- Fordert das Dienstmetadatendokument vom Datendienst an und interpretiert die zurückgegebenen Metadaten.  
  
    > [!NOTE]
    > Die zurückgegebenen Metadaten werden im Clientprojekt als EDMX-Datei gespeichert. Diese EDMX-Datei kann nicht mit dem Entity Data Model-Designer geöffnet werden, da sie nicht das gleiche Format wie eine vom Entity Framework verwendete EDMX-Datei aufweist. Sie können diese Metadatendatei mit dem XML-Editor oder einem beliebigen Texteditor anzeigen. Weitere Informationen finden Sie unter [ \[ MC-edmx \] : Entity Data Model für Data Services Packungs Format](/openspecs/windows_protocols/mc-edmx/5dff5e25-56a1-408b-9d44-bff6634c7d16).
  
- Generiert eine Darstellung des Diensts als Entitätscontainerklasse, die vom <xref:System.Data.Services.Client.DataServiceContext> erbt. Diese generierte Entitätscontainerklasse entspricht dem Entitätscontainer, den die Entity Data Model-Tools generieren. Weitere Informationen finden Sie unter [Übersicht über Object Services (Entity Framework)](/previous-versions/bb386871(v=vs.100)).  
  
- Generiert Datenklassen für die in den Dienstmetadaten erkannten Datenmodelltypen.  
  
- Fügt dem Projekt einen Verweis auf die `System.Data.Services.Client`-Assembly hinzu.  
  
 Weitere Informationen finden Sie unter Vorgehens [Weise: Hinzufügen eines Datendienst Verweises](how-to-add-a-data-service-reference-wcf-data-services.md).  
  
 Die Client Datendienst Klassen können auch mit dem [DataSvcUtil.exe](wcf-data-service-client-utility-datasvcutil-exe.md) Tool an der Eingabeaufforderung generiert werden. Weitere Informationen finden Sie unter Gewusst [wie: Manuelles Generieren von Client Datendienst Klassen](how-to-manually-generate-client-data-service-classes-wcf-data-services.md).  
  
## <a name="client-data-type-mapping"></a>Zuordnung von Clientdatentypen  

 Wenn Sie das Dialogfeld " **Dienstverweis hinzufügen** " in Visual Studio oder das Tool verwenden, `DataSvcUtil.exe` um Client Daten Klassen zu generieren, die auf einem odata-Feed basieren, werden die .NET Framework-Datentypen wie folgt den primitiven Typen aus dem Datenmodell zugeordnet:  
  
|Datenmodelltyp|Datentyp ".NET Framework"|  
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
  
 Weitere Informationen finden Sie im Abschnitt primitive Datentypen im Artikel [odata: Overview](https://www.odata.org/documentation/odata-version-2-0/overview/) .
  
## <a name="see-also"></a>Weitere Informationen

- [WCF Data Services-Clientbibliothek](wcf-data-services-client-library.md)
- [Schnellstart](quickstart-wcf-data-services.md)
