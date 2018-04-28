---
title: Steuern der Serialisierung und Deserialisierung mit SerializationBinder
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba8dcecf-acc7-467c-939d-021bbac797d4
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e41308de617fc02471ac2cb9769ec6e90e665e0b
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="controlling-serialization-and-deserialization-with-serializationbinder"></a><span data-ttu-id="ddb2d-102">Steuern der Serialisierung und Deserialisierung mit SerializationBinder</span><span class="sxs-lookup"><span data-stu-id="ddb2d-102">Controlling Serialization and Deserialization with SerializationBinder</span></span>
<span data-ttu-id="ddb2d-103">Ein Formatierungsprogramm überträgt während der Serialisierung die Informationen, die zum Erstellen einer Instanz eines Objekts mit dem korrekten Typ und der korrekten Version erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="ddb2d-103">During serialization, a formatter transmits the information required to create an instance of an object of the correct type and version.</span></span> <span data-ttu-id="ddb2d-104">Diese Informationen enthalten i. d. R. den vollständigen Typ- und Assemblynamen des Objekts.</span><span class="sxs-lookup"><span data-stu-id="ddb2d-104">This information generally includes the full type name and assembly name of the object.</span></span> <span data-ttu-id="ddb2d-105">Standardmäßig verwendet die Deserialisierung diese Informationen zum Erstellen einer Instanz eines identischen Objekts.</span><span class="sxs-lookup"><span data-stu-id="ddb2d-105">By default, deserialization uses this information to create an instance of an identical object.</span></span> <span data-ttu-id="ddb2d-106">Einige Benutzer müssen ggf. steuern, welche Klasse serialisiert und deserialisiert werden soll. Der Grund dafür kann sein, dass die ursprüngliche Klasse auf dem Computer, der die Deserialisierung ausführt, nicht vorhanden ist, dass die ursprüngliche Klasse die Assembly gewechselt hat oder dass auf dem Server und Client eine andere Version der Klasse erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="ddb2d-106">Some users may need to control which class to serialize and deserialize, either because the original class may not exist on the machine performing deserialization, the original class has moved between assemblies, or a different version of the class is required on the server and client.</span></span> <span data-ttu-id="ddb2d-107">Weitere Informationen finden Sie unter [Verwendung Serialisierungsbinder](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md).</span><span class="sxs-lookup"><span data-stu-id="ddb2d-107">For more information, see [Usage of Serialization Binder](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="ddb2d-108">Die Funktion ist nur verfügbar, wenn Sie <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> oder <xref:System.Runtime.Serialization.NetDataContractSerializer> verwenden.</span><span class="sxs-lookup"><span data-stu-id="ddb2d-108">This functionality is only available when using the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> or the <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span></span>  
  
## <a name="using-serializationbinder"></a><span data-ttu-id="ddb2d-109">Verwenden von SerializationBinder</span><span class="sxs-lookup"><span data-stu-id="ddb2d-109">Using SerializationBinder</span></span>  
 <span data-ttu-id="ddb2d-110"><xref:System.Runtime.Serialization.SerializationBinder> ist eine abstrakte Klasse, mit der die tatsächlichen Typen gesteuert werden, die während der Serialisierung und Deserialisierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ddb2d-110"><xref:System.Runtime.Serialization.SerializationBinder> is an abstract class used to control the actual types used during serialization and deserialization.</span></span> <span data-ttu-id="ddb2d-111">Zum Steuern der Typen, die während der Serialisierung und Deserialisierung verwendet werden, leiten Sie eine Klasse von <xref:System.Runtime.Serialization.SerializationBinder> ab und überschreiben die Methoden <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> und <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)>.</span><span class="sxs-lookup"><span data-stu-id="ddb2d-111">To control the types used during serialization and deserialization, derive a class from <xref:System.Runtime.Serialization.SerializationBinder> and override the <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> and <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)> methods.</span></span> <span data-ttu-id="ddb2d-112">Die <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)>-Methode verwendet einen <xref:System.Type> und gibt eine Assembly und einen Typnamen zurück.</span><span class="sxs-lookup"><span data-stu-id="ddb2d-112">The <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> method takes a <xref:System.Type> and returns an assembly and type name.</span></span> <span data-ttu-id="ddb2d-113">Die <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)>-Methode verwendet eine Assembly und einen Typnamen und gibt <xref:System.Type> zurück.</span><span class="sxs-lookup"><span data-stu-id="ddb2d-113">The <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)> method takes an assembly and type name and returns a <xref:System.Type>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddb2d-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ddb2d-114">See Also</span></span>  
 [<span data-ttu-id="ddb2d-115">Serialisierung und Deserialisierung</span><span class="sxs-lookup"><span data-stu-id="ddb2d-115">Serialization and Deserialization</span></span>](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md)  
 [<span data-ttu-id="ddb2d-116">Verwendung des Serialisierungsbinders</span><span class="sxs-lookup"><span data-stu-id="ddb2d-116">Usage of Serialization Binder</span></span>](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md)
