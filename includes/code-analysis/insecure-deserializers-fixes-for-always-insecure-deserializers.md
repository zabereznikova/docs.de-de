---
author: dotpaul
ms.author: paulming
ms.date: 05/01/2019
ms.topic: include
ms.openlocfilehash: cf944ae9ca200d34a1f0f32e68bf3aee73a9500a
ms.sourcegitcommit: c04535ad05e374fb269fcfc6509217755fbc0d54
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2020
ms.locfileid: "96590593"
---
- <span data-ttu-id="1a073-101">Verwenden Sie, wenn möglich, stattdessen ein sicheres Serialisierungsprogramm, und **lassen Sie nicht zu, dass ein Angreifer einen beliebigen zu deserialisierenden Typ angibt**.</span><span class="sxs-lookup"><span data-stu-id="1a073-101">If possible, use a secure serializer instead, and **don't allow an attacker to specify an arbitrary type to deserialize**.</span></span> <span data-ttu-id="1a073-102">Zu den sichereren serialisierungssoren zählen:</span><span class="sxs-lookup"><span data-stu-id="1a073-102">Some safer serializers include:</span></span>

  - <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>
  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>
  - <span data-ttu-id="1a073-103"><xref:System.Web.Script.Serialization.JavaScriptSerializer?displayProperty=nameWithType> -Nie verwenden <xref:System.Web.Script.Serialization.SimpleTypeResolver?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="1a073-103"><xref:System.Web.Script.Serialization.JavaScriptSerializer?displayProperty=nameWithType> - Never use <xref:System.Web.Script.Serialization.SimpleTypeResolver?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1a073-104">Wenn Sie einen Typresolver verwenden müssen, beschränken Sie deserialisierte Typen auf eine erwartete Liste.</span><span class="sxs-lookup"><span data-stu-id="1a073-104">If you must use a type resolver, restrict deserialized types to an expected list.</span></span>
  - <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>
  - <span data-ttu-id="1a073-105">Newtonsoft JSON.net: Verwenden Sie typamehandult. None.</span><span class="sxs-lookup"><span data-stu-id="1a073-105">Newtonsoft Json.NET - Use TypeNameHandling.None.</span></span> <span data-ttu-id="1a073-106">Wenn Sie einen anderen Wert für typamehanding verwenden müssen, beschränken Sie deserialisierte Typen auf eine erwartete Liste mit einem benutzerdefinierten iserializationbinder.</span><span class="sxs-lookup"><span data-stu-id="1a073-106">If you must use another value for TypeNameHandling, restrict deserialized types to an expected list with a custom ISerializationBinder.</span></span>
  - <span data-ttu-id="1a073-107">Protokollpuffer</span><span class="sxs-lookup"><span data-stu-id="1a073-107">Protocol Buffers</span></span>

- <span data-ttu-id="1a073-108">Sorgen Sie dafür, dass die serialisierten Daten manipuliert werden.</span><span class="sxs-lookup"><span data-stu-id="1a073-108">Make the serialized data tamper-proof.</span></span> <span data-ttu-id="1a073-109">Signieren Sie die serialisierten Daten nach der Serialisierung kryptografisch.</span><span class="sxs-lookup"><span data-stu-id="1a073-109">After serialization, cryptographically sign the serialized data.</span></span> <span data-ttu-id="1a073-110">Überprüfen Sie vor der Deserialisierung die kryptografische Signatur.</span><span class="sxs-lookup"><span data-stu-id="1a073-110">Before deserialization, validate the cryptographic signature.</span></span> <span data-ttu-id="1a073-111">Schützen Sie den Kryptografieschlüssel vor der Offenlegung, und entwerfen Sie Schlüssel Drehungen.</span><span class="sxs-lookup"><span data-stu-id="1a073-111">Protect the cryptographic key from being disclosed and design for key rotations.</span></span>
