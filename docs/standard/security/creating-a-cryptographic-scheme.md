---
title: Erstellen eines kryptografischen Schemas
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- encryption [.NET Framework], creating cryptographic schemes
- cryptography [.NET Framework], creating cryptographic schemes
ms.assetid: d40c509f-5a5e-46cc-94cb-a951e9ab6843
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: b0aabdc9150aea73ad9078b0e9ee92b2abd03e17
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="creating-a-cryptographic-scheme"></a><span data-ttu-id="bde3f-102">Erstellen eines kryptografischen Schemas</span><span class="sxs-lookup"><span data-stu-id="bde3f-102">Creating a Cryptographic Scheme</span></span>
<span data-ttu-id="bde3f-103">Die kryptografischen Komponenten von .NET Framework können kombiniert werden, um unterschiedliche Schemas zum Ver- und Entschlüsseln von Daten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bde3f-103">The cryptographic components of the .NET Framework can be combined to create different schemes to encrypt and decrypt data.</span></span>  
  
 <span data-ttu-id="bde3f-104">Für ein einfaches kryptografisches Schema zum Ver- und Entschlüsseln von Daten können die folgenden Schritte angegeben sein: </span><span class="sxs-lookup"><span data-stu-id="bde3f-104">A simple cryptographic scheme for encrypting and decrypting data might specify the following steps:</span></span>  
  
1.  <span data-ttu-id="bde3f-105">Jeder Teilnehmer generiert ein Paar aus privatem und öffentlichem Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="bde3f-105">Each party generates a public/private key pair.</span></span>  
  
2.  <span data-ttu-id="bde3f-106">Die Teilnehmer tauschen ihre öffentlichen Schlüssel aus.</span><span class="sxs-lookup"><span data-stu-id="bde3f-106">The parties exchange their public keys.</span></span>  
  
3.  <span data-ttu-id="bde3f-107">Jeder Teilnehmer generiert einen geheimen Schlüssel, z. B. für die TripleDES-Verschlüsselung, und verschlüsselt den neu erstellen Schlüssel mit dem öffentlichen Schlüssel des anderen Teilnehmers.</span><span class="sxs-lookup"><span data-stu-id="bde3f-107">Each party generates a secret key for TripleDES encryption, for example, and encrypts the newly created key using the other's public key.</span></span>  
  
4.  <span data-ttu-id="bde3f-108">Jeder Teilnehmer sendet die Daten an den jeweils anderen Teilnehmer und kombiniert den geheimen Schlüssel des anderen in einer bestimmten Folge mit dem eigenen Schlüssel, um einen neuen geheimen Schlüssel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bde3f-108">Each party sends the data to the other and combines the other's secret key with its own, in a particular order, to create a new secret key.</span></span>  
  
5.  <span data-ttu-id="bde3f-109">Danach beginnen die Teilnehmer eine Konversation mit symmetrischer Verschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="bde3f-109">The parties then initiate a conversation using symmetric encryption.</span></span>  
  
 <span data-ttu-id="bde3f-110">Das Erstellen eines kryptografischen Schemas ist keine leichte Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="bde3f-110">Creating a cryptographic scheme is not a trivial task.</span></span> <span data-ttu-id="bde3f-111">Weitere Informationen zur Verwendung von Kryptografie finden Sie im Thema "Cryptography" in der Platform SDK-Dokumentation unter "http://msdn.microsoft.com/library".</span><span class="sxs-lookup"><span data-stu-id="bde3f-111">For more information on using cryptography, see the Cryptography topic in the Platform SDK documentation at http://msdn.microsoft.com/library.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bde3f-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bde3f-112">See Also</span></span>  
 [<span data-ttu-id="bde3f-113">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="bde3f-113">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
