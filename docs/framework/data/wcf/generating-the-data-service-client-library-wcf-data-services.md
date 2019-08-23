---
title: Generieren der Datendienst-Clientbibliothek (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- Add Service Reference dialog box
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
ms.openlocfilehash: 14ea550715c1b224945137f123eed3b53e56cead
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918644"
---
# <a name="generating-the-data-service-client-library-wcf-data-services"></a><span data-ttu-id="860b2-102">Generieren der Datendienst-Clientbibliothek (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="860b2-102">Generating the Data Service Client Library (WCF Data Services)</span></span>
<span data-ttu-id="860b2-103">Ein Datendienst, der [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] implementiert, kann ein dienstmetadatendokument zurückgeben, das das Datenmodell beschreibt, das [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] vom Feed verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="860b2-103">A data service that implements the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] can return a service metadata document that describes the data model exposed by the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed.</span></span> <span data-ttu-id="860b2-104">Weitere Informationen finden [Sie unter odata: Dienstmetadatendokument](https://go.microsoft.com/fwlink/?LinkId=186070).</span><span class="sxs-lookup"><span data-stu-id="860b2-104">For more information, see [OData: Service Metadata Document](https://go.microsoft.com/fwlink/?LinkId=186070).</span></span> <span data-ttu-id="860b2-105">Sie können das Dialogfeld " **Dienstverweis hinzufügen** " in Visual Studio verwenden, um einem [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-basierten Dienst einen Verweis hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="860b2-105">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-based service.</span></span> <span data-ttu-id="860b2-106">Wenn Sie dieses Tool verwenden, um einen Verweis auf die von einem [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] -Feed in einem Client Projekt zurückgegebenen Metadaten hinzuzufügen, führt es die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="860b2-106">When you use this tool to add a reference to the metadata returned by an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed in a client project, it performs the following actions:</span></span>  
  
- <span data-ttu-id="860b2-107">Fordert das Dienstmetadatendokument vom Datendienst an und interpretiert die zurückgegebenen Metadaten.</span><span class="sxs-lookup"><span data-stu-id="860b2-107">Requests the service metadata document from the data service and interprets the returned metadata.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="860b2-108">Die zurückgegebenen Metadaten werden im Clientprojekt als EDMX-Datei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="860b2-108">The returned metadata is stored in the client project as an .edmx file.</span></span> <span data-ttu-id="860b2-109">Diese EDMX-Datei kann nicht mit dem Entity Data Model-Designer geöffnet werden, da sie nicht das gleiche Format wie eine vom Entity Framework verwendete EDMX-Datei aufweist.</span><span class="sxs-lookup"><span data-stu-id="860b2-109">This .edmx file cannot be opened by using the Entity Data Model designer because it does not have the same format an .edmx file used by the Entity Framework.</span></span> <span data-ttu-id="860b2-110">Sie können diese Metadatendatei mit dem XML-Editor oder einem beliebigen Texteditor anzeigen.</span><span class="sxs-lookup"><span data-stu-id="860b2-110">You can view this metadata file by using the XML editor or any text editor.</span></span> <span data-ttu-id="860b2-111">Weitere Informationen finden Sie unter [ \[MC-edmx\]: Entity Data Model für Data Services Paket Format](https://go.microsoft.com/fwlink/?LinkID=178833) Spezifikation</span><span class="sxs-lookup"><span data-stu-id="860b2-111">For more information, see the [\[MC-EDMX\]: Entity Data Model for Data Services Packaging Format](https://go.microsoft.com/fwlink/?LinkID=178833) specification</span></span>  
  
- <span data-ttu-id="860b2-112">Generiert eine Darstellung des Diensts als Entitätscontainerklasse, die vom <xref:System.Data.Services.Client.DataServiceContext> erbt.</span><span class="sxs-lookup"><span data-stu-id="860b2-112">Generates a representation of the service as an entity container class that inherits from <xref:System.Data.Services.Client.DataServiceContext>.</span></span> <span data-ttu-id="860b2-113">Diese generierte Entitätscontainerklasse entspricht dem Entitätscontainer, den die Entity Data Model-Tools generieren.</span><span class="sxs-lookup"><span data-stu-id="860b2-113">This generated entity container class resembles the entity container that the Entity Data Model tools generate.</span></span> <span data-ttu-id="860b2-114">Weitere Informationen finden Sie unter [Übersicht über Object Services (Entity Framework)](https://docs.microsoft.com/previous-versions/bb386871(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="860b2-114">For more information, see [Object Services Overview (Entity Framework)](https://docs.microsoft.com/previous-versions/bb386871(v=vs.100)).</span></span>  
  
- <span data-ttu-id="860b2-115">Generiert Datenklassen für die in den Dienstmetadaten erkannten Datenmodelltypen.</span><span class="sxs-lookup"><span data-stu-id="860b2-115">Generates data classes for the data model types that it discovers in the service metadata.</span></span>  
  
- <span data-ttu-id="860b2-116">Fügt dem Projekt einen Verweis auf die `System.Data.Services.Client`-Assembly hinzu.</span><span class="sxs-lookup"><span data-stu-id="860b2-116">Adds a reference to the `System.Data.Services.Client` assembly to the project.</span></span>  
  
 <span data-ttu-id="860b2-117">Weitere Informationen finden Sie unter [Vorgehensweise: Fügen Sie einen Datendienst](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)Verweis hinzu.</span><span class="sxs-lookup"><span data-stu-id="860b2-117">For more information, see [How to: Add a Data Service Reference](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="860b2-118">Die Client Datendienst Klassen können auch mit dem Tool [DataSvcUtil. exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) an der Eingabeaufforderung generiert werden.</span><span class="sxs-lookup"><span data-stu-id="860b2-118">The client data service classes can also be generated by using the [DataSvcUtil.exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) tool at the command prompt.</span></span> <span data-ttu-id="860b2-119">Weitere Informationen finden Sie unter [Vorgehensweise: Manuelles Generieren von Client Daten](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md)Dienst Klassen.</span><span class="sxs-lookup"><span data-stu-id="860b2-119">For more information, see [How to: Manually Generate Client Data Service Classes](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).</span></span>  
  
## <a name="client-data-type-mapping"></a><span data-ttu-id="860b2-120">Zuordnung von Clientdatentypen</span><span class="sxs-lookup"><span data-stu-id="860b2-120">Client Data Type Mapping</span></span>  
 <span data-ttu-id="860b2-121">Wenn Sie das Dialogfeld " **Dienstverweis hinzufügen** " in Visual Studio `DataSvcUtil.exe` oder das Tool verwenden, um Client Daten Klassen zu generieren [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] , die auf einem-Feed basieren, werden die .NET Framework-Datentypen wie folgt den primitiven Typen aus dem Datenmodell zugeordnet:</span><span class="sxs-lookup"><span data-stu-id="860b2-121">When you use the **Add Service Reference** dialog in Visual Studio or the `DataSvcUtil.exe` tool to generate client data classes that are based on an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed, the .NET Framework data types are mapped to the primitive types from the data model as follows:</span></span>  
  
|<span data-ttu-id="860b2-122">Datenmodelltyp</span><span class="sxs-lookup"><span data-stu-id="860b2-122">Data model type</span></span>|<span data-ttu-id="860b2-123">.NET Framework-Datentyp</span><span class="sxs-lookup"><span data-stu-id="860b2-123">.NET Framework data type</span></span>|  
|---------------------|------------------------------|  
|`Edm.Binary`|<span data-ttu-id="860b2-124"><xref:System.Byte> `[]`</span><span class="sxs-lookup"><span data-stu-id="860b2-124"><xref:System.Byte> `[]`</span></span>|  
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
  
 <span data-ttu-id="860b2-125">Weitere Informationen finden [Sie unter odata: Primitive Datentypen](https://go.microsoft.com/fwlink/?LinkId=186072).</span><span class="sxs-lookup"><span data-stu-id="860b2-125">For more information, see [OData: Primitive Data Types](https://go.microsoft.com/fwlink/?LinkId=186072).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="860b2-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="860b2-126">See also</span></span>

- [<span data-ttu-id="860b2-127">WCF Data Services-Clientbibliothek</span><span class="sxs-lookup"><span data-stu-id="860b2-127">WCF Data Services Client Library</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
- [<span data-ttu-id="860b2-128">Schnellstart</span><span class="sxs-lookup"><span data-stu-id="860b2-128">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
