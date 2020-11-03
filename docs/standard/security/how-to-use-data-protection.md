---
title: 'Vorgehensweise: Verwenden des Datenschutzes'
description: Erfahren Sie, wie Sie Datenschutz durchzugreifen auf die Datenschutz-API (Data Protection API, DPAPI) in .NET verwenden.
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DPAPI
- encryption [.NET], data protection API
- data [.NET], decryption
- ProtectedMemory class, about ProtectedMemory class
- ProtectedData class, about ProtectedData class
- cryptography [.NET], data protection API
- data protection API [.NET]
- decryption
- data [.NET], encryption
ms.assetid: 606698b0-cb1a-42ca-beeb-0bea34205d20
ms.openlocfilehash: d3fe7ef3ddbc6e75a248101829b11a8abcb3c15a
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282054"
---
# <a name="how-to-use-data-protection"></a><span data-ttu-id="7527a-103">Vorgehensweise: Verwenden des Datenschutzes</span><span class="sxs-lookup"><span data-stu-id="7527a-103">How to: Use Data Protection</span></span>

> [!NOTE]
> <span data-ttu-id="7527a-104">Dieser Artikel bezieht sich auf Windows.</span><span class="sxs-lookup"><span data-stu-id="7527a-104">This article applies to Windows.</span></span>
>
> <span data-ttu-id="7527a-105">Weitere Informationen zu ASP.net Core finden Sie unter [ASP.net Core Datenschutz](/aspnet/core/security/data-protection/introduction).</span><span class="sxs-lookup"><span data-stu-id="7527a-105">For information about ASP.NET Core, see [ASP.NET Core Data Protection](/aspnet/core/security/data-protection/introduction).</span></span>

<span data-ttu-id="7527a-106">.Net bietet Zugriff auf die Datenschutz-API (Data Protection API, DPAPI), mit der Sie Daten mithilfe von Informationen aus dem aktuellen Benutzerkonto oder-Computer verschlüsseln können.</span><span class="sxs-lookup"><span data-stu-id="7527a-106">.NET provides access to the data protection API (DPAPI), which allows you to encrypt data using information from the current user account or computer.</span></span>  <span data-ttu-id="7527a-107">Wenn Sie die Datenschutz-API verwenden, umgehen Sie die schwierige Aufgabe, einen kryptografischen Schlüssel explizit zu generieren und zu speichern.</span><span class="sxs-lookup"><span data-stu-id="7527a-107">When you use the DPAPI, you alleviate the difficult problem of explicitly generating and storing a cryptographic key.</span></span>  
  
<span data-ttu-id="7527a-108">Verwenden Sie die <xref:System.Security.Cryptography.ProtectedData>-Klasse, um eine Kopie eines Bytearrays zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="7527a-108">Use the <xref:System.Security.Cryptography.ProtectedData> class to encrypt a copy of an array of bytes.</span></span> <span data-ttu-id="7527a-109">Diese Funktionalität ist in .NET Framework, .net Core und .net 5 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7527a-109">This functionality is available in .NET Framework, .NET Core, and .NET 5.</span></span>  <span data-ttu-id="7527a-110">Sie können angeben, dass Daten, die über das aktuelle Benutzerkonto verschlüsselt wurden, nur über dasselbe Benutzerkonto oder über jedes Konto auf dem Computer entschlüsselt werden können.</span><span class="sxs-lookup"><span data-stu-id="7527a-110">You can specify that data encrypted by the current user account can be decrypted only by the same user account, or you can specify that data encrypted by the current user account can be decrypted by any account on the computer.</span></span>  <span data-ttu-id="7527a-111">In der <xref:System.Security.Cryptography.DataProtectionScope>-Enumeration finden Sie eine ausführliche Beschreibung der <xref:System.Security.Cryptography.ProtectedData>-Optionen.</span><span class="sxs-lookup"><span data-stu-id="7527a-111">See the <xref:System.Security.Cryptography.DataProtectionScope> enumeration for a detailed description of <xref:System.Security.Cryptography.ProtectedData> options.</span></span>  
  
## <a name="encrypt-data-to-a-file-or-stream-using-data-protection"></a><span data-ttu-id="7527a-112">Verschlüsseln von Daten in einer Datei oder einem Stream mithilfe von Datenschutz</span><span class="sxs-lookup"><span data-stu-id="7527a-112">Encrypt data to a file or stream using data protection</span></span>  
  
1. <span data-ttu-id="7527a-113">Erstellen Sie eine zufällige Entropie.</span><span class="sxs-lookup"><span data-stu-id="7527a-113">Create random entropy.</span></span>  
  
2. <span data-ttu-id="7527a-114">Rufen Sie die statische <xref:System.Security.Cryptography.ProtectedData.Protect%2A>-Methode auf, wobei Sie ein Array zu verschlüsselnder Bytes, die Entropie und den Datenschutzbereich übergeben.</span><span class="sxs-lookup"><span data-stu-id="7527a-114">Call the static <xref:System.Security.Cryptography.ProtectedData.Protect%2A> method while passing an array of bytes to encrypt, the entropy, and the data protection scope.</span></span>  
  
3. <span data-ttu-id="7527a-115">Schreiben Sie die verschlüsselten Daten in eine Datei oder einen Stream.</span><span class="sxs-lookup"><span data-stu-id="7527a-115">Write the encrypted data to a file or stream.</span></span>  
  
### <a name="to-decrypt-data-from-a-file-or-stream-using-data-protection"></a><span data-ttu-id="7527a-116">So entschlüsseln Sie Daten aus einer Datei oder einem Stream mithilfe von Datenschutz</span><span class="sxs-lookup"><span data-stu-id="7527a-116">To decrypt data from a file or stream using data protection</span></span>  
  
1. <span data-ttu-id="7527a-117">Lesen Sie die verschlüsselten Daten aus einer Datei oder einem Stream.</span><span class="sxs-lookup"><span data-stu-id="7527a-117">Read the encrypted data from a file or stream.</span></span>  
  
2. <span data-ttu-id="7527a-118">Rufen Sie die statische <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A>-Methode auf, wobei Sie ein Array zu entschlüsselnder Bytes und den Datenschutzbereich übergeben.</span><span class="sxs-lookup"><span data-stu-id="7527a-118">Call the static <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A> method while passing an array of bytes to decrypt and the data protection scope.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7527a-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7527a-119">Example</span></span>

<span data-ttu-id="7527a-120">Im folgenden Codebeispiel werden zwei Arten von Verschlüsselung und Entschlüsselung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="7527a-120">The following code example demonstrates two forms of encryption and decryption.</span></span>  <span data-ttu-id="7527a-121">Im Codebeispiel wird zunächst ein im Arbeitsspeicher befindliches Array aus Bytes verschlüsselt und anschließend entschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="7527a-121">First, the code example encrypts and then decrypts an in-memory array of bytes.</span></span>  <span data-ttu-id="7527a-122">Danach wird eine Kopie eines Bytearrays verschlüsselt, wird diese Kopie in einer Datei gespeichert, werden die Daten aus der Datei zurückgeladen und werden die Daten entschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="7527a-122">Next, the code example encrypts a copy of a byte array, saves it to a file, loads the data back from the file, and then decrypts the data.</span></span>  <span data-ttu-id="7527a-123">Im Beispiel werden die ursprünglichen Daten, die verschlüsselten Daten und die entschlüsselten Daten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7527a-123">The example displays the original data, the encrypted data, and the decrypted data.</span></span>

[!code-csharp[DPAPI-HowTO#1](../../../samples/snippets/csharp/VS_Snippets_CLR/DPAPI-HowTO/cs/sample.cs#1)]
[!code-vb[DPAPI-HowTO#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DPAPI-HowTO/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7527a-124">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="7527a-124">Compiling the Code</span></span>  

<span data-ttu-id="7527a-125">Dieses Beispiel wird nur kompiliert und ausgeführt, wenn .NET Framework und unter Windows ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7527a-125">This example compiles and runs only when targeting .NET Framework and running on Windows.</span></span>

- <span data-ttu-id="7527a-126">Fügen Sie einen Verweis auf `System.Security.dll` ein.</span><span class="sxs-lookup"><span data-stu-id="7527a-126">Include a reference to `System.Security.dll`.</span></span>  
  
- <span data-ttu-id="7527a-127">Fügen Sie die Namespaces <xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography> und <xref:System.Text> ein.</span><span class="sxs-lookup"><span data-stu-id="7527a-127">Include the <xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography>, and <xref:System.Text> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7527a-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7527a-128">See also</span></span>

- [<span data-ttu-id="7527a-129">Kryptografiemodell</span><span class="sxs-lookup"><span data-stu-id="7527a-129">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="7527a-130">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="7527a-130">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="7527a-131">Plattformübergreifende Kryptografie</span><span class="sxs-lookup"><span data-stu-id="7527a-131">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.ProtectedMemory>
- <xref:System.Security.Cryptography.ProtectedData>
- [<span data-ttu-id="7527a-132">ASP.net Core Datenschutz</span><span class="sxs-lookup"><span data-stu-id="7527a-132">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
