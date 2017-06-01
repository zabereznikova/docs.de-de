---
title: "Generieren der Datendienst-Clientbibliothek (WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Dienstverweis hinzufügen (Dialogfeld)"
  - "Clientanwendungen, WCF Data Services"
  - "WCF Data Services, Clientbibliothek"
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Generieren der Datendienst-Clientbibliothek (WCF Data Services)
Ein Datendienst, der [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] implementiert, kann ein Dienstmetadatendokument zurückgeben, in dem das vom [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Feed verfügbar gemachte Datenmodell beschrieben wird.  Weitere Informationen finden Sie in [OData: Dienstmetadatendokument](http://go.microsoft.com/fwlink/?LinkId=186070). Sie können das Dialogfeld **Dienstverweis hinzufügen** in Visual Studio verwenden, um einem [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-basierten Dienst einen Verweis hinzuzufügen.  Wenn Sie dieses Tool verwenden, um den von einem [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Feed in einem Clientprojekt zurückgegebenen Metadaten einen Verweis hinzuzufügen, führt es die folgenden Aktionen aus:  
  
-   Fordert das Dienstmetadatendokument vom Datendienst an und interpretiert die zurückgegebenen Metadaten.  
  
    > [!NOTE]
    >  Die zurückgegebenen Metadaten werden im Clientprojekt als EDMX\-Datei gespeichert.  Diese EDMX\-Datei kann nicht mit dem Entity Data Model\-Designer geöffnet werden, da sie nicht das gleiche Format wie eine vom Entity Framework verwendete EDMX\-Datei aufweist.  Sie können diese Metadatendatei mit dem XML\-Editor oder einem beliebigen Texteditor anzeigen.  Weitere Informationen finden Sie in der Spezifikation [\[MC\-EDMX\]: Entity Data Model for Data Services Packaging Format](http://go.microsoft.com/fwlink/?LinkID=178833).  
  
-   Generiert eine Darstellung des Diensts als Entitätscontainerklasse, die vom <xref:System.Data.Services.Client.DataServiceContext> erbt.  Diese generierte Entitätscontainerklasse entspricht dem Entitätscontainer, den die Entity Data Model\-Tools generieren.  Weitere Informationen finden Sie unter [Object Services Overview \(Entity Framework\)](http://msdn.microsoft.com/de-de/43014cf9-c9cb-4538-bfbb-197820b60038).  
  
-   Generiert Datenklassen für die in den Dienstmetadaten erkannten Datenmodelltypen.  
  
-   Fügt dem Projekt einen Verweis auf die `System.Data.Services.Client`\-Assembly hinzu.  
  
 Weitere Informationen finden Sie unter [Gewusst wie: Hinzufügen eines Datendienstverweises](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).  
  
 Die Clientdatendienstklassen können auch an der Eingabeaufforderung mit dem Tool [DataSvcUtil.exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) generiert werden.  Weitere Informationen finden Sie unter [Gewusst wie: Manuelles Generieren von Clientdatendienstklassen](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).  
  
## Zuordnung von Clientdatentypen  
 Wenn Sie mithilfe des Dialogfelds **Dienstverweis hinzufügen** in Visual Studio oder des `DataSvcUtil.exe`\-Tools Clientdatenklassen generieren, die auf einem [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Feed basieren, werden die .NET Framework\-Datentypen wie folgt den primitiven Typen aus dem Datenmodell zugeordnet:  
  
|Datenmodelltyp|.NET Framework\-Datentyp|  
|--------------------|------------------------------|  
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
  
 Weitere Informationen finden Sie unter [OData: Primitive Datentypen](http://go.microsoft.com/fwlink/?LinkId=186072).  
  
## Siehe auch  
 [WCF Data Services\-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)   
 [Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)