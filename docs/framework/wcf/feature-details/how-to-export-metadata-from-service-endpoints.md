---
title: 'Vorgehensweise: Exportieren von Metadaten aus Dienstendpunkten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b6c4dfd0-f270-43ec-961a-e16eb6af2f2c
ms.openlocfilehash: c253358b68cf18a23bab4d12d4ad760874103bff
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96246406"
---
# <a name="how-to-export-metadata-from-service-endpoints"></a><span data-ttu-id="19667-102">Vorgehensweise: Exportieren von Metadaten aus Dienstendpunkten</span><span class="sxs-lookup"><span data-stu-id="19667-102">How to: Export Metadata from Service Endpoints</span></span>

<span data-ttu-id="19667-103">In diesem Thema wird erklärt, wie Sie Metadaten aus Dienstendpunkten exportieren.</span><span class="sxs-lookup"><span data-stu-id="19667-103">This topic explains how to export metadata from service endpoints.</span></span>  
  
### <a name="to-export-metadata-from-service-endpoints"></a><span data-ttu-id="19667-104">So exportieren Sie Metadaten aus Dienstendpunkten</span><span class="sxs-lookup"><span data-stu-id="19667-104">To export metadata from service endpoints</span></span>  
  
1. <span data-ttu-id="19667-105">Erstellen Sie ein neues Visual Studio-Konsolenanwendungsprojekt.</span><span class="sxs-lookup"><span data-stu-id="19667-105">Create a new Visual Studio Console App Project.</span></span> <span data-ttu-id="19667-106">Fügen Sie den in den folgenden Schritten gezeigten Code der erzeugten Datei "Program.cs" innerhalb der main()-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="19667-106">Add the code shown in the following steps in the generated Program.cs file within the main() method.</span></span>  
  
2. <span data-ttu-id="19667-107">Erstellen Sie eine <xref:System.ServiceModel.Description.WsdlExporter>.</span><span class="sxs-lookup"><span data-stu-id="19667-107">Create a <xref:System.ServiceModel.Description.WsdlExporter>.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#1)]
     [!code-vb[S_UEWsdlExporter#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#1)]  
  
3. <span data-ttu-id="19667-108">Legen Sie die <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A>-Eigenschaft auf einen der <xref:System.ServiceModel.Description.PolicyVersion>-Enumerationswerte fest.</span><span class="sxs-lookup"><span data-stu-id="19667-108">Set the <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> property to one of the values from the <xref:System.ServiceModel.Description.PolicyVersion> enumeration.</span></span> <span data-ttu-id="19667-109">In diesem Beispiel wird der Wert auf <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A> festgelegt. Dies entspricht der WS-Richtlinie 1.5.</span><span class="sxs-lookup"><span data-stu-id="19667-109">This sample sets the value to <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A> which corresponds to WS-Policy 1.5.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#2)]
     [!code-vb[S_UEWsdlExporter#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#2)]  
  
4. <span data-ttu-id="19667-110">Erstellen Sie ein Array mit <xref:System.ServiceModel.Description.ServiceEndpoint>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="19667-110">Create an array of <xref:System.ServiceModel.Description.ServiceEndpoint> objects.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#3)]
     [!code-vb[S_UEWsdlExporter#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#3)]  
  
5. <span data-ttu-id="19667-111">Exportieren Sie Metadaten für jeden Dienstendpunkt.</span><span class="sxs-lookup"><span data-stu-id="19667-111">Export metadata for each service endpoint.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#4)]
     [!code-vb[S_UEWsdlExporter#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#4)]  
  
6. <span data-ttu-id="19667-112">Stellen Sie sicher, dass während des Exportprozesses keine Fehler aufgetreten sind, und rufen Sie die Metadaten ab.</span><span class="sxs-lookup"><span data-stu-id="19667-112">Check to make sure no errors occurred during the export process and retrieve the metadata.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#5)]
     [!code-vb[S_UEWsdlExporter#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#5)]  
  
7. <span data-ttu-id="19667-113">Sie können die Metadaten jetzt verwenden, beispielsweise indem Sie sie mithilfe eines Aufrufs der <xref:System.ServiceModel.Description.MetadataSet.WriteTo%28System.Xml.XmlWriter%29>-Methode in eine Datei schreiben.</span><span class="sxs-lookup"><span data-stu-id="19667-113">You can now use the metadata, such as write it to a file by calling the <xref:System.ServiceModel.Description.MetadataSet.WriteTo%28System.Xml.XmlWriter%29> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19667-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="19667-114">Example</span></span>  

 <span data-ttu-id="19667-115">Unten ist die vollständige Codeauflistung für dieses Beispiel angegeben.</span><span class="sxs-lookup"><span data-stu-id="19667-115">The following is the full code listing for this example.</span></span>  
  
 [!code-csharp[S_UEWsdlExporter#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#0)]
 [!code-vb[S_UEWsdlExporter#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="19667-116">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="19667-116">Compiling the Code</span></span>  

 <span data-ttu-id="19667-117">Verweisen Sie beim Kompilieren der Datei "Program.cs" auf "System.ServiceModel.dll".</span><span class="sxs-lookup"><span data-stu-id="19667-117">When compiling Program.cs reference System.ServiceModel.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19667-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="19667-118">See also</span></span>

- [<span data-ttu-id="19667-119">Übersicht über die Metadatenarchitektur</span><span class="sxs-lookup"><span data-stu-id="19667-119">Metadata Architecture Overview</span></span>](metadata-architecture-overview.md)
- [<span data-ttu-id="19667-120">Verwenden von Metadaten</span><span class="sxs-lookup"><span data-stu-id="19667-120">Using Metadata</span></span>](using-metadata.md)
- [<span data-ttu-id="19667-121">Endpunkte: Adressen, Bindungen und Verträge</span><span class="sxs-lookup"><span data-stu-id="19667-121">Endpoints: Addresses, Bindings, and Contracts</span></span>](endpoints-addresses-bindings-and-contracts.md)
