---
title: Hinzufügen eines Dienstverweises in einem Projekt für die portable Teilmenge
ms.date: 03/30/2017
ms.assetid: 61ccfe0f-a34b-40ca-8f5e-725fa1b8095e
ms.openlocfilehash: e9a0d3fbc75a8c64af892f74acedfc41dc115da3
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687702"
---
# <a name="add-service-reference-in-a-portable-subset-project"></a><span data-ttu-id="b870b-102">Hinzufügen eines Dienstverweises in einem Projekt für die portable Teilmenge</span><span class="sxs-lookup"><span data-stu-id="b870b-102">Add Service Reference in a Portable Subset Project</span></span>

<span data-ttu-id="b870b-103">Projekte für Portable Teilmengen ermöglichen es .net-assemblyprogrammierern, eine einzelne Quell Struktur und ein Buildsystem zu verwalten, während mehrere .net-Implementierungen (Desktop, Silverlight, Windows Phone und Xbox) unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="b870b-103">Portable subset projects enable .NET assembly programmers to maintain a single source tree and build system while still supporting multiple .NET implementations (desktop, Silverlight, Windows Phone, and Xbox).</span></span> <span data-ttu-id="b870b-104">Projekte für Portable Teilmengen verweisen nur auf Portable Bibliotheken, die .NET-Assemblys sind, die für jede .NET-Implementierung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="b870b-104">Portable subset projects only reference portable libraries that are .NET assemblies that can be used on any .NET implementation.</span></span>
  
## <a name="add-service-reference-details"></a><span data-ttu-id="b870b-105">Details zu "Dienstverweis hinzufügen"</span><span class="sxs-lookup"><span data-stu-id="b870b-105">Add Service Reference Details</span></span>  
 <span data-ttu-id="b870b-106">Wenn Sie einem Projekt für portable Teilmengen einen Dienstverweis hinzufügen, werden die folgenden Einschränkungen erzwungen:</span><span class="sxs-lookup"><span data-stu-id="b870b-106">When adding a service reference in a portable subset project the following restrictions are enforced:</span></span>  
  
1. <span data-ttu-id="b870b-107">Für <xref:System.Xml.Serialization.XmlSerializer> sind nur literale Codierungen zulässig.</span><span class="sxs-lookup"><span data-stu-id="b870b-107">For <xref:System.Xml.Serialization.XmlSerializer>, only literal encodings are allowed.</span></span> <span data-ttu-id="b870b-108">SOAP-Codierungen generieren während des Imports einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="b870b-108">SOAP encodings generate an error during import.</span></span>  
  
2. <span data-ttu-id="b870b-109">Bei Diensten, die <xref:System.Runtime.Serialization.DataContractSerializer>-Szenarien verwenden, wird ein Datenvertrag-Ersatzzeichen bereitgestellt, um sicherzustellen, dass wiederverwendete Typen nur aus der portablen Teilmenge stammen.</span><span class="sxs-lookup"><span data-stu-id="b870b-109">For services that use <xref:System.Runtime.Serialization.DataContractSerializer> scenarios, a data contract surrogate is provided to ensure that reused types come only from the portable subset.</span></span>  
  
3. <span data-ttu-id="b870b-110">Endpunkte, die auf Bindungen basieren, die in portablen Bibliotheken nicht unterstützt werden (alle Bindungen außer <xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.WSHttpBinding> ohne Transaktionsfluss, zuverlässige Sitzungen oder MTOM-Codierung und die entsprechenden benutzerdefinierten Bindungen), werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="b870b-110">Endpoints which rely on bindings not supported in portable libraries (all bindings except <xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.WSHttpBinding> without transaction flow, reliable sessions, or MTOM encoding, and equivalent custom bindings) are ignored.</span></span>  
  
4. <span data-ttu-id="b870b-111">Nachrichtenheader werden vor dem Import aus allen Nachrichtenbeschreibungen in sämtlichen Vorgängen gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b870b-111">Message headers are deleted from all message descriptions in all operations before import.</span></span>  
  
5. <span data-ttu-id="b870b-112">Die nicht portablen Attribute <xref:System.ComponentModel.DesignerCategoryAttribute>, <xref:System.SerializableAttribute> und <xref:System.ServiceModel.TransactionFlowAttribute> werden aus generiertem Clientproxycode entfernt.</span><span class="sxs-lookup"><span data-stu-id="b870b-112">Non-portable attributes <xref:System.ComponentModel.DesignerCategoryAttribute>, <xref:System.SerializableAttribute>, and <xref:System.ServiceModel.TransactionFlowAttribute> are removed from generated client proxy code.</span></span>  
  
6. <span data-ttu-id="b870b-113">Die nicht portablen Eigenschaften ProtectionLevel, SessionMode, IsInitiating und IsTerminating werden aus ,  und  entfernt.</span><span class="sxs-lookup"><span data-stu-id="b870b-113">Non-portable properties ProtectionLevel, SessionMode, IsInitiating, IsTerminating are removed from <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.OperationContractAttribute>, and <xref:System.ServiceModel.FaultContractAttribute>.</span></span>  
  
7. <span data-ttu-id="b870b-114">Alle Dienstvorgänge werden auf dem Clientproxy als asynchrone Vorgänge generiert.</span><span class="sxs-lookup"><span data-stu-id="b870b-114">All service operations are generated as asynchronous operations on the client proxy.</span></span>  
  
8. <span data-ttu-id="b870b-115">Generierte Clientkonstruktoren, die nicht portable Typen verwenden, werden entfernt.</span><span class="sxs-lookup"><span data-stu-id="b870b-115">Generated client constructors which use non-portable types are removed.</span></span>  
  
9. <span data-ttu-id="b870b-116">Eine <xref:System.Net.CookieContainer>-Instanz wird für den generierten Client verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="b870b-116">A <xref:System.Net.CookieContainer> instance is exposed on the generated client.</span></span>  
  
10. <span data-ttu-id="b870b-117">Am Anfang der Datei wird ein Kommentar eingefügt, der die Assembly und die Version des Code-Generators identifiziert: `// This code was auto-generated by Microsoft.VisualStudio.Portable.AddServiceReference, version 1.0.0.0`</span><span class="sxs-lookup"><span data-stu-id="b870b-117">A comment is inserted at the top of the file identifying the assembly and version of the code generator:`// This code was auto-generated by Microsoft.VisualStudio.Portable.AddServiceReference, version 1.0.0.0`</span></span>  
  
11. <span data-ttu-id="b870b-118">Die <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b870b-118">The <xref:System.Runtime.Serialization.ISerializable> interface is not supported.</span></span>  
  
12. <span data-ttu-id="b870b-119">Net.Tcp- und PollingDuplex-Bindungen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b870b-119">Net.Tcp and PollingDuplex bindings are not supported</span></span>  
  
13. <span data-ttu-id="b870b-120"><xref:System.Runtime.Serialization.DataContractSerializer> wird immer bei Fehlern verwendet.</span><span class="sxs-lookup"><span data-stu-id="b870b-120">The <xref:System.Runtime.Serialization.DataContractSerializer> will always be used for faults.</span></span>  
  
14. <span data-ttu-id="b870b-121"><xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> wird in Projekten für portable Teilmengen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b870b-121"><xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> is not supported in portable subset projects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b870b-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b870b-122">See also</span></span>

- [<span data-ttu-id="b870b-123">Zugreifen auf Dienste mithilfe eines WCF-Clients</span><span class="sxs-lookup"><span data-stu-id="b870b-123">Accessing Services Using a WCF Client</span></span>](accessing-services-using-a-wcf-client.md)
- [<span data-ttu-id="b870b-124">Portable Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="b870b-124">Portable Class Library</span></span>](../cross-platform/portable-class-library.md)
