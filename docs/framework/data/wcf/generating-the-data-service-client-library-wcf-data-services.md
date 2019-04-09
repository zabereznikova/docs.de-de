---
title: Generieren der Datendienst-Clientbibliothek (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- Add Service Reference dialog box
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
ms.openlocfilehash: 96b7bfabef589464e99e808d19f0dee6cfb23536
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225819"
---
# <a name="generating-the-data-service-client-library-wcf-data-services"></a><span data-ttu-id="dc1d9-102">Generieren der Datendienst-Clientbibliothek (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="dc1d9-102">Generating the Data Service Client Library (WCF Data Services)</span></span>
<span data-ttu-id="dc1d9-103">Ein Datendienst, die implementiert die [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] kann ein dienstmetadatendokument an, die von verfügbar gemachten Datenmodell beschreibt Zurückgeben der [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed.</span><span class="sxs-lookup"><span data-stu-id="dc1d9-103">A data service that implements the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] can return a service metadata document that describes the data model exposed by the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed.</span></span> <span data-ttu-id="dc1d9-104">Weitere Informationen finden Sie unter [OData: Service Metadatendokument](https://go.microsoft.com/fwlink/?LinkId=186070).</span><span class="sxs-lookup"><span data-stu-id="dc1d9-104">For more information, see [OData: Service Metadata Document](https://go.microsoft.com/fwlink/?LinkId=186070).</span></span> <span data-ttu-id="dc1d9-105">Können Sie die **Hinzufügen eines Dienstverweises** Dialogfeld in Visual Studio zum Hinzufügen eines Verweises auf ein [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-basierten Dienst.</span><span class="sxs-lookup"><span data-stu-id="dc1d9-105">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-based service.</span></span> <span data-ttu-id="dc1d9-106">Wenn Sie dieses Tool verwenden, um einen Verweis auf das vom zurückgegebenen Metadaten Hinzufügen einer [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed in einem Clientprojekt die folgenden Aktionen ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="dc1d9-106">When you use this tool to add a reference to the metadata returned by an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed in a client project, it performs the following actions:</span></span>  
  
-   <span data-ttu-id="dc1d9-107">Fordert das Dienstmetadatendokument vom Datendienst an und interpretiert die zurückgegebenen Metadaten.</span><span class="sxs-lookup"><span data-stu-id="dc1d9-107">Requests the service metadata document from the data service and interprets the returned metadata.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dc1d9-108">Die zurückgegebenen Metadaten werden im Clientprojekt als EDMX-Datei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="dc1d9-108">The returned metadata is stored in the client project as an .edmx file.</span></span> <span data-ttu-id="dc1d9-109">Diese EDMX-Datei kann nicht mit dem Entity Data Model-Designer geöffnet werden, da sie nicht das gleiche Format wie eine vom Entity Framework verwendete EDMX-Datei aufweist.</span><span class="sxs-lookup"><span data-stu-id="dc1d9-109">This .edmx file cannot be opened by using the Entity Data Model designer because it does not have the same format an .edmx file used by the Entity Framework.</span></span> <span data-ttu-id="dc1d9-110">Sie können diese Metadatendatei mit dem XML-Editor oder einem beliebigen Texteditor anzeigen.</span><span class="sxs-lookup"><span data-stu-id="dc1d9-110">You can view this metadata file by using the XML editor or any text editor.</span></span> <span data-ttu-id="dc1d9-111">Weitere Informationen finden Sie unter den [ \[MC-EDMX\]: Entity Data Model für Data Services Packaging Format](https://go.microsoft.com/fwlink/?LinkID=178833) Spezifikation</span><span class="sxs-lookup"><span data-stu-id="dc1d9-111">For more information, see the [\[MC-EDMX\]: Entity Data Model for Data Services Packaging Format](https://go.microsoft.com/fwlink/?LinkID=178833) specification</span></span>  
  
-   <span data-ttu-id="dc1d9-112">Generiert eine Darstellung des Diensts als Entitätscontainerklasse, die vom <xref:System.Data.Services.Client.DataServiceContext> erbt.</span><span class="sxs-lookup"><span data-stu-id="dc1d9-112">Generates a representation of the service as an entity container class that inherits from <xref:System.Data.Services.Client.DataServiceContext>.</span></span> <span data-ttu-id="dc1d9-113">Diese generierte Entitätscontainerklasse entspricht dem Entitätscontainer, den die Entity Data Model-Tools generieren.</span><span class="sxs-lookup"><span data-stu-id="dc1d9-113">This generated entity container class resembles the entity container that the Entity Data Model tools generate.</span></span> <span data-ttu-id="dc1d9-114">Weitere Informationen finden Sie unter [Übersicht über Object Services (Entity Framework)](https://docs.microsoft.com/previous-versions/bb386871(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="dc1d9-114">For more information, see [Object Services Overview (Entity Framework)](https://docs.microsoft.com/previous-versions/bb386871(v=vs.100)).</span></span>  
  
-   <span data-ttu-id="dc1d9-115">Generiert Datenklassen für die in den Dienstmetadaten erkannten Datenmodelltypen.</span><span class="sxs-lookup"><span data-stu-id="dc1d9-115">Generates data classes for the data model types that it discovers in the service metadata.</span></span>  
  
-   <span data-ttu-id="dc1d9-116">Fügt dem Projekt einen Verweis auf die `System.Data.Services.Client`-Assembly hinzu.</span><span class="sxs-lookup"><span data-stu-id="dc1d9-116">Adds a reference to the `System.Data.Services.Client` assembly to the project.</span></span>  
  
 <span data-ttu-id="dc1d9-117">Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen ein Datendienstverweises](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="dc1d9-117">For more information, see [How to: Add a Data Service Reference](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="dc1d9-118">Die Client-Datendienstklassen können auch generiert werden, mithilfe der [DataSvcUtil.exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) Tool an der Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="dc1d9-118">The client data service classes can also be generated by using the [DataSvcUtil.exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) tool at the command prompt.</span></span> <span data-ttu-id="dc1d9-119">Weitere Informationen finden Sie unter [Vorgehensweise: Manuelles Generieren von Clientdatendienstklassen](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="dc1d9-119">For more information, see [How to: Manually Generate Client Data Service Classes](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).</span></span>  
  
## <a name="client-data-type-mapping"></a><span data-ttu-id="dc1d9-120">Zuordnung von Clientdatentypen</span><span class="sxs-lookup"><span data-stu-id="dc1d9-120">Client Data Type Mapping</span></span>  
 <span data-ttu-id="dc1d9-121">Bei Verwendung der **Hinzufügen eines Dienstverweises** Dialogfeld in Visual Studio oder die `DataSvcUtil.exe` clientdatenklassen generieren auf der Grundlage von eine [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed, den primitiven Typen von der .NET Framework-Datentypen zugeordnet sind die Datenmodell wie folgt:</span><span class="sxs-lookup"><span data-stu-id="dc1d9-121">When you use the **Add Service Reference** dialog in Visual Studio or the `DataSvcUtil.exe` tool to generate client data classes that are based on an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed, the .NET Framework data types are mapped to the primitive types from the data model as follows:</span></span>  
  
|<span data-ttu-id="dc1d9-122">Datenmodelltyp</span><span class="sxs-lookup"><span data-stu-id="dc1d9-122">Data model type</span></span>|<span data-ttu-id="dc1d9-123">.NET Framework-Datentyp</span><span class="sxs-lookup"><span data-stu-id="dc1d9-123">.NET Framework data type</span></span>|  
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
  
 <span data-ttu-id="dc1d9-124">Weitere Informationen finden Sie unter [OData: Primitive Datentypen](https://go.microsoft.com/fwlink/?LinkId=186072).</span><span class="sxs-lookup"><span data-stu-id="dc1d9-124">For more information, see [OData: Primitive Data Types](https://go.microsoft.com/fwlink/?LinkId=186072).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc1d9-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc1d9-125">See also</span></span>

- [<span data-ttu-id="dc1d9-126">WCF Data Services-Clientbibliothek</span><span class="sxs-lookup"><span data-stu-id="dc1d9-126">WCF Data Services Client Library</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
- [<span data-ttu-id="dc1d9-127">Schnellstart</span><span class="sxs-lookup"><span data-stu-id="dc1d9-127">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
