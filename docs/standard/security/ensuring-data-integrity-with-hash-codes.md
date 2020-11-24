---
title: Gewährleisten der Datenintegrität über Hashcodes
description: Erfahren Sie, wie Sie die Datenintegrität mithilfe von Hashcodes in .net gewährleisten. Ein Hashwert ist ein numerischer Wert einer festen Länge, der die Daten eindeutig identifiziert.
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- generating hash
- verifying hash codes
- cryptography [.NET], hash
- data integrity
- checking hash codes
- encryption [.NET], hash
- hash
ms.assetid: 33660f33-b70f-4dca-8c87-ab35cfc2961a
ms.openlocfilehash: 7f5e1d54efa3a5ccf28f2e0863a9bc9ccb80f894
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689744"
---
# <a name="ensuring-data-integrity-with-hash-codes"></a><span data-ttu-id="328e8-104">Gewährleisten der Datenintegrität über Hashcodes</span><span class="sxs-lookup"><span data-stu-id="328e8-104">Ensuring Data Integrity with Hash Codes</span></span>

<span data-ttu-id="328e8-105">Ein Hashwert ist ein numerischer Wert einer festen Länge, der die Daten eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="328e8-105">A hash value is a numeric value of a fixed length that uniquely identifies data.</span></span> <span data-ttu-id="328e8-106">Hashwerte stellen große Mengen von Daten als viel kleinere numerische Werte dar, damit sie mit digitalen Signaturen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="328e8-106">Hash values represent large amounts of data as much smaller numeric values, so they are used with digital signatures.</span></span> <span data-ttu-id="328e8-107">Sie können einen Hashwert effizienter signieren als den größeren Wert.</span><span class="sxs-lookup"><span data-stu-id="328e8-107">You can sign a hash value more efficiently than signing the larger value.</span></span> <span data-ttu-id="328e8-108">Hashwerte sind auch zum Überprüfen der Integrität der Daten nützlich, die über unsichere Kanäle gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="328e8-108">Hash values are also useful for verifying the integrity of data sent through insecure channels.</span></span> <span data-ttu-id="328e8-109">Der Hashwert der empfangenen Daten kann mit dem Hashwert der Daten verglichen werden, da sie gesendet wurden, um festzustellen, ob die Daten verändert wurden.</span><span class="sxs-lookup"><span data-stu-id="328e8-109">The hash value of received data can be compared to the hash value of data as it was sent to determine whether the data was altered.</span></span>  
  
<span data-ttu-id="328e8-110">In diesem Thema wird beschrieben, wie Hashcodes mit den Klassen im <xref:System.Security.Cryptography>-Namespace generiert und überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="328e8-110">This topic describes how to generate and verify hash codes by using the classes in the <xref:System.Security.Cryptography> namespace.</span></span>  
  
## <a name="generating-a-hash"></a><span data-ttu-id="328e8-111">Generieren eines Hashs</span><span class="sxs-lookup"><span data-stu-id="328e8-111">Generating a Hash</span></span>

 <span data-ttu-id="328e8-112">Die verwalteten Hashklassen können entweder ein Bytearray oder ein verwaltetes Streamobjekt hashen.</span><span class="sxs-lookup"><span data-stu-id="328e8-112">The managed hash classes can hash either an array of bytes or a managed stream object.</span></span> <span data-ttu-id="328e8-113">Im folgenden Beispiel wird der SHA1-Hashalgorithmus verwendet, um einen Hashwert für eine Zeichenfolge zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="328e8-113">The following example uses the SHA1 hash algorithm to create a hash value for a string.</span></span> <span data-ttu-id="328e8-114">Im Beispiel wird die <xref:System.Text.UnicodeEncoding>-Klasse verwendet, um die Zeichenfolge in ein Bytearray zu konvertieren, dem mithilfe der <xref:System.Security.Cryptography.SHA256>-Klasse ein Hash hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="328e8-114">The example uses the <xref:System.Text.UnicodeEncoding> class to convert the string into an array of bytes that are hashed by using the <xref:System.Security.Cryptography.SHA256> class.</span></span> <span data-ttu-id="328e8-115">Der Hashwert wird dann in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="328e8-115">The hash value is then displayed to the console.</span></span>  

 [!code-csharp[GeneratingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/generatingahash/cs/program.cs#1)]
 [!code-vb[GeneratingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/generatingahash/vb/program.vb#1)]  
  
 <span data-ttu-id="328e8-116">Dieser Code zeigt die folgende Zeichenfolge in der Konsole an:</span><span class="sxs-lookup"><span data-stu-id="328e8-116">This code will display the following string to the console:</span></span>  
  
 `185 203 236 22 3 228 27 130 87 23 244 15 87 88 14 43 37 61 106 224 81 172 224 211 104 85 194 197 194 25 120 217`  
  
## <a name="verifying-a-hash"></a><span data-ttu-id="328e8-117">Überprüfen eines Hashs</span><span class="sxs-lookup"><span data-stu-id="328e8-117">Verifying a Hash</span></span>

 <span data-ttu-id="328e8-118">Die Daten können mit einem Hashwert verglichen werden, um die Integrität zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="328e8-118">Data can be compared to a hash value to determine its integrity.</span></span> <span data-ttu-id="328e8-119">In der Regel werden die Daten zu einem bestimmten Zeitpunkt gehasht, und der Hashwert wird entsprechend geschützt.</span><span class="sxs-lookup"><span data-stu-id="328e8-119">Usually, data is hashed at a certain time and the hash value is protected in some way.</span></span> <span data-ttu-id="328e8-120">Zu einem späteren Zeitpunkt werden die Daten erneut gehasht und mit dem geschützten Wert verglichen.</span><span class="sxs-lookup"><span data-stu-id="328e8-120">At a later time, the data can be hashed again and compared to the protected value.</span></span> <span data-ttu-id="328e8-121">Wenn die Hashwerte übereinstimmen, wurden die Daten nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="328e8-121">If the hash values match, the data has not been altered.</span></span> <span data-ttu-id="328e8-122">Wenn die Werte nicht übereinstimmen, sind die Daten beschädigt wurden.</span><span class="sxs-lookup"><span data-stu-id="328e8-122">If the values do not match, the data has been corrupted.</span></span> <span data-ttu-id="328e8-123">Damit dieses System funktioniert, muss der geschützte Hash verschlüsselt oder vor allen nicht vertrauenswürdigen Parteien geheim gehalten werden.</span><span class="sxs-lookup"><span data-stu-id="328e8-123">For this system to work, the protected hash must be encrypted or kept secret from all untrusted parties.</span></span>  
  
 <span data-ttu-id="328e8-124">Im folgenden Beispiel wird der vorherige Hashwert einer Zeichenfolge mit einem neuen Hashwert verglichen.</span><span class="sxs-lookup"><span data-stu-id="328e8-124">The following example compares the previous hash value of a string to a new hash value.</span></span> <span data-ttu-id="328e8-125">In diesem Beispiel wird jedes Byte der Hashwerte durchlaufen und verglichen.</span><span class="sxs-lookup"><span data-stu-id="328e8-125">This example loops through each byte of the hash values and makes a comparison.</span></span>  
  
 [!code-csharp[VerifyingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/verifyingahash/cs/program.cs#1)]
 [!code-vb[VerifyingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/verifyingahash/vb/program.vb#1)]  
  
 <span data-ttu-id="328e8-126">Wenn die beiden Hashwerte übereinstimmen, zeigt dieser Code Folgendes in der Konsole an:</span><span class="sxs-lookup"><span data-stu-id="328e8-126">If the two hash values match, this code displays the following to the console:</span></span>  
  
```console  
The hash codes match.  
```  
  
 <span data-ttu-id="328e8-127">Wenn sie nicht übereinstimmen, zeigt der Code Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="328e8-127">If they do not match, the code displays the following:</span></span>  
  
```console  
The hash codes do not match.  
```  
  
## <a name="see-also"></a><span data-ttu-id="328e8-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="328e8-128">See also</span></span>

- [<span data-ttu-id="328e8-129">Kryptografiemodell</span><span class="sxs-lookup"><span data-stu-id="328e8-129">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="328e8-130">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="328e8-130">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="328e8-131">Plattformübergreifende Kryptografie</span><span class="sxs-lookup"><span data-stu-id="328e8-131">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="328e8-132">ASP.net Core Datenschutz</span><span class="sxs-lookup"><span data-stu-id="328e8-132">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
