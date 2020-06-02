---
title: Gewährleisten der Datenintegrität über Hashcodes
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- generating hash
- verifying hash codes
- cryptography [.NET Framework], hash
- data integrity
- checking hash codes
- encryption [.NET Framework], hash
- hash
ms.assetid: 33660f33-b70f-4dca-8c87-ab35cfc2961a
ms.openlocfilehash: 4938cd75af32caa4f9da6ed682f18e9f6c73ad5b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288341"
---
# <a name="ensuring-data-integrity-with-hash-codes"></a><span data-ttu-id="c02d4-102">Gewährleisten der Datenintegrität über Hashcodes</span><span class="sxs-lookup"><span data-stu-id="c02d4-102">Ensuring Data Integrity with Hash Codes</span></span>
<span data-ttu-id="c02d4-103">Ein Hashwert ist ein numerischer Wert einer festen Länge, der die Daten eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="c02d4-103">A hash value is a numeric value of a fixed length that uniquely identifies data.</span></span> <span data-ttu-id="c02d4-104">Hashwerte stellen große Mengen von Daten als viel kleinere numerische Werte dar, damit sie mit digitalen Signaturen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c02d4-104">Hash values represent large amounts of data as much smaller numeric values, so they are used with digital signatures.</span></span> <span data-ttu-id="c02d4-105">Sie können einen Hashwert effizienter signieren als den größeren Wert.</span><span class="sxs-lookup"><span data-stu-id="c02d4-105">You can sign a hash value more efficiently than signing the larger value.</span></span> <span data-ttu-id="c02d4-106">Hashwerte sind auch zum Überprüfen der Integrität der Daten nützlich, die über unsichere Kanäle gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="c02d4-106">Hash values are also useful for verifying the integrity of data sent through insecure channels.</span></span> <span data-ttu-id="c02d4-107">Der Hashwert der empfangenen Daten kann mit dem Hashwert der Daten verglichen werden, da sie gesendet wurden, um festzustellen, ob die Daten verändert wurden.</span><span class="sxs-lookup"><span data-stu-id="c02d4-107">The hash value of received data can be compared to the hash value of data as it was sent to determine whether the data was altered.</span></span>  
  
 <span data-ttu-id="c02d4-108">In diesem Thema wird beschrieben, wie Hashcodes mit den Klassen im <xref:System.Security.Cryptography?displayProperty=nameWithType>-Namespace generiert und überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="c02d4-108">This topic describes how to generate and verify hash codes by using the classes in the <xref:System.Security.Cryptography?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="generating-a-hash"></a><span data-ttu-id="c02d4-109">Generieren eines Hashs</span><span class="sxs-lookup"><span data-stu-id="c02d4-109">Generating a Hash</span></span>  
 <span data-ttu-id="c02d4-110">Die verwalteten Hashklassen können entweder ein Bytearray oder ein verwaltetes Streamobjekt hashen.</span><span class="sxs-lookup"><span data-stu-id="c02d4-110">The managed hash classes can hash either an array of bytes or a managed stream object.</span></span> <span data-ttu-id="c02d4-111">Im folgenden Beispiel wird der SHA1-Hashalgorithmus verwendet, um einen Hashwert für eine Zeichenfolge zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c02d4-111">The following example uses the SHA1 hash algorithm to create a hash value for a string.</span></span> <span data-ttu-id="c02d4-112">Im Beispiel wird die <xref:System.Text.UnicodeEncoding>-Klasse verwendet, um die Zeichenfolge in ein Bytearray zu konvertieren, dem mithilfe der <xref:System.Security.Cryptography.SHA1Managed>-Klasse ein Hash hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c02d4-112">The example uses the <xref:System.Text.UnicodeEncoding> class to convert the string into an array of bytes that are hashed by using the <xref:System.Security.Cryptography.SHA1Managed> class.</span></span> <span data-ttu-id="c02d4-113">Der Hashwert wird dann in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c02d4-113">The hash value is then displayed to the console.</span></span>  

 <span data-ttu-id="c02d4-114">Microsoft empfiehlt aufgrund der Konflikte mit SHA1 SHA256 oder höher.</span><span class="sxs-lookup"><span data-stu-id="c02d4-114">Due to collision problems with SHA1, Microsoft recommends SHA256 or better.</span></span>
  
 [!code-csharp[GeneratingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/generatingahash/cs/program.cs#1)]
 [!code-vb[GeneratingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/generatingahash/vb/program.vb#1)]  
  
 <span data-ttu-id="c02d4-115">Dieser Code zeigt die folgende Zeichenfolge in der Konsole an:</span><span class="sxs-lookup"><span data-stu-id="c02d4-115">This code will display the following string to the console:</span></span>  
  
 `59 4 248 102 77 97 142 201 210 12 224 93 25 41 100 197 213 134 130 135`  
  
## <a name="verifying-a-hash"></a><span data-ttu-id="c02d4-116">Überprüfen eines Hashs</span><span class="sxs-lookup"><span data-stu-id="c02d4-116">Verifying a Hash</span></span>  
 <span data-ttu-id="c02d4-117">Die Daten können mit einem Hashwert verglichen werden, um die Integrität zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="c02d4-117">Data can be compared to a hash value to determine its integrity.</span></span> <span data-ttu-id="c02d4-118">In der Regel werden die Daten zu einem bestimmten Zeitpunkt gehasht, und der Hashwert wird entsprechend geschützt.</span><span class="sxs-lookup"><span data-stu-id="c02d4-118">Usually, data is hashed at a certain time and the hash value is protected in some way.</span></span> <span data-ttu-id="c02d4-119">Zu einem späteren Zeitpunkt werden die Daten erneut gehasht und mit dem geschützten Wert verglichen.</span><span class="sxs-lookup"><span data-stu-id="c02d4-119">At a later time, the data can be hashed again and compared to the protected value.</span></span> <span data-ttu-id="c02d4-120">Wenn die Hashwerte übereinstimmen, wurden die Daten nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="c02d4-120">If the hash values match, the data has not been altered.</span></span> <span data-ttu-id="c02d4-121">Wenn die Werte nicht übereinstimmen, sind die Daten beschädigt wurden.</span><span class="sxs-lookup"><span data-stu-id="c02d4-121">If the values do not match, the data has been corrupted.</span></span> <span data-ttu-id="c02d4-122">Damit dieses System funktioniert, muss der geschützte Hash verschlüsselt oder vor allen nicht vertrauenswürdigen Parteien geheim gehalten werden.</span><span class="sxs-lookup"><span data-stu-id="c02d4-122">For this system to work, the protected hash must be encrypted or kept secret from all untrusted parties.</span></span>  
  
 <span data-ttu-id="c02d4-123">Im folgenden Beispiel wird der vorherige Hashwert einer Zeichenfolge mit einem neuen Hashwert verglichen.</span><span class="sxs-lookup"><span data-stu-id="c02d4-123">The following example compares the previous hash value of a string to a new hash value.</span></span> <span data-ttu-id="c02d4-124">In diesem Beispiel wird jedes Byte der Hashwerte durchlaufen und verglichen.</span><span class="sxs-lookup"><span data-stu-id="c02d4-124">This example loops through each byte of the hash values and makes a comparison.</span></span>  
  
 [!code-csharp[VerifyingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/verifyingahash/cs/program.cs#1)]
 [!code-vb[VerifyingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/verifyingahash/vb/program.vb#1)]  
  
 <span data-ttu-id="c02d4-125">Wenn die beiden Hashwerte übereinstimmen, zeigt dieser Code Folgendes in der Konsole an:</span><span class="sxs-lookup"><span data-stu-id="c02d4-125">If the two hash values match, this code displays the following to the console:</span></span>  
  
```console  
The hash codes match.  
```  
  
 <span data-ttu-id="c02d4-126">Wenn sie nicht übereinstimmen, zeigt der Code Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="c02d4-126">If they do not match, the code displays the following:</span></span>  
  
```console  
The hash codes do not match.  
```  
  
## <a name="see-also"></a><span data-ttu-id="c02d4-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c02d4-127">See also</span></span>

- [<span data-ttu-id="c02d4-128">Kryptografiedienste</span><span class="sxs-lookup"><span data-stu-id="c02d4-128">Cryptographic Services</span></span>](cryptographic-services.md)
