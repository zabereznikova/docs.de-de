---
title: Datenübertragung und Serialisierung
ms.date: 03/30/2017
helpviewer_keywords:
- data serialization [WCF]
- data transfer [WCF]
ms.assetid: 0f03c635-f3e7-4c5c-9463-3cb0135e221e
ms.openlocfilehash: 5192030fa2eda45431dd8a3765603d3081b93fa3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595317"
---
# <a name="data-transfer-and-serialization"></a><span data-ttu-id="ad717-102">Datenübertragung und Serialisierung</span><span class="sxs-lookup"><span data-stu-id="ad717-102">Data Transfer and Serialization</span></span>
<span data-ttu-id="ad717-103">In einem verbundenen System müssen Dienste und Clients Daten austauschen, um Aufgaben auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ad717-103">In a connected system, services and clients depend on the exchange of data to accomplish any task.</span></span> <span data-ttu-id="ad717-104">Als Entwickler eines Diensts oder Clients müssen Sie auch wissen, wie Windows Communication Foundation (WCF) verarbeitet Daten und der Datenserialisierung um Anwendungen zu erstellen, die effizient und leicht zu warten sind.</span><span class="sxs-lookup"><span data-stu-id="ad717-104">As a developer of a service or client, you must also understand how Windows Communication Foundation (WCF) handles data and data serialization in order to create applications that are efficient and easy to maintain.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ad717-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ad717-105">In This Section</span></span>  
 [<span data-ttu-id="ad717-106">Angeben von Datenübertragung in Dienstverträgen</span><span class="sxs-lookup"><span data-stu-id="ad717-106">Specifying Data Transfer in Service Contracts</span></span>](../../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md)  
 <span data-ttu-id="ad717-107">Beschreibt die grundlegenden Aspekte der Datenübertragung in Diensten.</span><span class="sxs-lookup"><span data-stu-id="ad717-107">Describes the basic concepts of data transfer in services.</span></span>  
  
 [<span data-ttu-id="ad717-108">Verwenden von Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="ad717-108">Using Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 <span data-ttu-id="ad717-109">Beschreibt, was Datenverträge sind und wie sie erstellt und verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ad717-109">Describes what data contracts are and how to create and use them.</span></span>  
  
 [<span data-ttu-id="ad717-110">Datenvertragsserialisierer</span><span class="sxs-lookup"><span data-stu-id="ad717-110">Data Contract Serializer</span></span>](../../../../docs/framework/wcf/feature-details/data-contract-serializer.md)  
 <span data-ttu-id="ad717-111">Beschreibt, wie die Datenserialisierung mit der <xref:System.Runtime.Serialization.DataContractSerializer>-Klasse oder einer Erweiterung der <xref:System.Runtime.Serialization.XmlObjectSerializer>-Klasse durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ad717-111">Describes how to accomplish serialization of data with the <xref:System.Runtime.Serialization.DataContractSerializer> class or any extension of the <xref:System.Runtime.Serialization.XmlObjectSerializer> class.</span></span>  
  
 [<span data-ttu-id="ad717-112">Verwenden der XmlSerializer-Klasse</span><span class="sxs-lookup"><span data-stu-id="ad717-112">Using the XmlSerializer Class</span></span>](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md)  
 <span data-ttu-id="ad717-113">Beschreibt, wie und warum die <xref:System.Xml.Serialization.XmlSerializer>-Klasse, eine Alternative zur <xref:System.Runtime.Serialization.DataContractSerializer>-Klasse, verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ad717-113">Describes how and why to use the <xref:System.Xml.Serialization.XmlSerializer> class, an alternative to the <xref:System.Runtime.Serialization.DataContractSerializer> class.</span></span>  
  
 [<span data-ttu-id="ad717-114">Verwenden von Nachrichtenverträgen</span><span class="sxs-lookup"><span data-stu-id="ad717-114">Using Message Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-message-contracts.md)  
 <span data-ttu-id="ad717-115">Beschreibt, wie Nachrichtenverträge die genaue Steuerung von SOAP-Nachrichten ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="ad717-115">Describes how message contracts allow fine control over SOAP messages.</span></span>  
  
 [<span data-ttu-id="ad717-116">Verwenden der Message-Klasse</span><span class="sxs-lookup"><span data-stu-id="ad717-116">Using the Message Class</span></span>](../../../../docs/framework/wcf/feature-details/using-the-message-class.md)  
 <span data-ttu-id="ad717-117">Beschreibt, wie Nachrichtenklassenfunktionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ad717-117">Describes how to use Message class features.</span></span>  
  
 [<span data-ttu-id="ad717-118">Filtern</span><span class="sxs-lookup"><span data-stu-id="ad717-118">Filtering</span></span>](../../../../docs/framework/wcf/feature-details/filtering.md)  
 <span data-ttu-id="ad717-119">Beschreibt die Filterung, die eine Vorverarbeitung von Nachrichten auf der Grundlage verschiedener Kriterien ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="ad717-119">Describes filtering, which enables pre-processing of a message based on various criteria.</span></span>  
  
 [<span data-ttu-id="ad717-120">Umfangreiche Daten und Streaming</span><span class="sxs-lookup"><span data-stu-id="ad717-120">Large Data and Streaming</span></span>](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md)  
 <span data-ttu-id="ad717-121">Beschreibt, wie ein großer Datenblock gesendet wird, z.&#160;B. eine Binärdatei.</span><span class="sxs-lookup"><span data-stu-id="ad717-121">Describes how to send a large block of data, such as a binary file.</span></span>  
  
 [<span data-ttu-id="ad717-122">Sicherheitsüberlegungen zu Daten</span><span class="sxs-lookup"><span data-stu-id="ad717-122">Security Considerations for Data</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md)  
 <span data-ttu-id="ad717-123">Beschreibt Dinge, auf die bei der Programmierung der Datenübertragung und Datenserialisierung geachtet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="ad717-123">Describes items to be aware of when programming data transfer and serialization.</span></span>  
  
 [<span data-ttu-id="ad717-124">Datenübertragungsarchitektur: Übersicht</span><span class="sxs-lookup"><span data-stu-id="ad717-124">Data Transfer Architectural Overview</span></span>](../../../../docs/framework/wcf/feature-details/data-transfer-architectural-overview.md)  
 <span data-ttu-id="ad717-125">Beschreibt einen Überblick über den Gesamtentwurf der Datenübertragung in WCF.</span><span class="sxs-lookup"><span data-stu-id="ad717-125">Describes a view of the overall design of data transfer in WCF.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ad717-126">Referenz</span><span class="sxs-lookup"><span data-stu-id="ad717-126">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
  
 <xref:System.Xml.Serialization.XmlSerializer>  
  
 <xref:System.Runtime.Serialization>  
  
 <xref:System.Xml.Serialization>  
  
## <a name="related-sections"></a><span data-ttu-id="ad717-127">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="ad717-127">Related Sections</span></span>  
 [<span data-ttu-id="ad717-128">Erweitern von Encodern und Serialisierungsprogrammen</span><span class="sxs-lookup"><span data-stu-id="ad717-128">Extending Encoders and Serializers</span></span>](../../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md)  
  
## <a name="see-also"></a><span data-ttu-id="ad717-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad717-129">See also</span></span>
- [<span data-ttu-id="ad717-130">Bewährte Methoden: Versionsverwaltung von Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="ad717-130">Best Practices: Data Contract Versioning</span></span>](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)
- [<span data-ttu-id="ad717-131">Dienstversionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="ad717-131">Service Versioning</span></span>](../../../../docs/framework/wcf/service-versioning.md)
