---
title: Erstellen eines kryptografischen Schemas
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- encryption [.NET Framework], creating cryptographic schemes
- cryptography [.NET Framework], creating cryptographic schemes
ms.assetid: d40c509f-5a5e-46cc-94cb-a951e9ab6843
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2db6d4229ac777801aff792c86fe0e5e9a1b4994
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44197892"
---
# <a name="creating-a-cryptographic-scheme"></a><span data-ttu-id="60d18-102">Erstellen eines kryptografischen Schemas</span><span class="sxs-lookup"><span data-stu-id="60d18-102">Creating a Cryptographic Scheme</span></span>
<span data-ttu-id="60d18-103">Die kryptografischen Komponenten von .NET Framework können kombiniert werden, um unterschiedliche Schemas zum Ver- und Entschlüsseln von Daten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="60d18-103">The cryptographic components of the .NET Framework can be combined to create different schemes to encrypt and decrypt data.</span></span>  
  
 <span data-ttu-id="60d18-104">Für ein einfaches kryptografisches Schema zum Ver- und Entschlüsseln von Daten können die folgenden Schritte angegeben sein: </span><span class="sxs-lookup"><span data-stu-id="60d18-104">A simple cryptographic scheme for encrypting and decrypting data might specify the following steps:</span></span>  
  
1.  <span data-ttu-id="60d18-105">Jeder Teilnehmer generiert ein Paar aus privatem und öffentlichem Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="60d18-105">Each party generates a public/private key pair.</span></span>  
  
2.  <span data-ttu-id="60d18-106">Die Teilnehmer tauschen ihre öffentlichen Schlüssel aus.</span><span class="sxs-lookup"><span data-stu-id="60d18-106">The parties exchange their public keys.</span></span>  
  
3.  <span data-ttu-id="60d18-107">Jeder Teilnehmer generiert einen geheimen Schlüssel, z. B. für die TripleDES-Verschlüsselung, und verschlüsselt den neu erstellen Schlüssel mit dem öffentlichen Schlüssel des anderen Teilnehmers.</span><span class="sxs-lookup"><span data-stu-id="60d18-107">Each party generates a secret key for TripleDES encryption, for example, and encrypts the newly created key using the other's public key.</span></span>  
  
4.  <span data-ttu-id="60d18-108">Jeder Teilnehmer sendet die Daten an den jeweils anderen Teilnehmer und kombiniert den geheimen Schlüssel des anderen in einer bestimmten Folge mit dem eigenen Schlüssel, um einen neuen geheimen Schlüssel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="60d18-108">Each party sends the data to the other and combines the other's secret key with its own, in a particular order, to create a new secret key.</span></span>  
  
5.  <span data-ttu-id="60d18-109">Danach beginnen die Teilnehmer eine Konversation mit symmetrischer Verschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="60d18-109">The parties then initiate a conversation using symmetric encryption.</span></span>  
  
 <span data-ttu-id="60d18-110">Das Erstellen eines kryptografischen Schemas ist keine leichte Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="60d18-110">Creating a cryptographic scheme is not a trivial task.</span></span> <span data-ttu-id="60d18-111">Weitere Informationen zur Verwendung von Kryptografie finden Sie unter dem Thema "Cryptography" in der Platform SDK-Dokumentation unter http://msdn.microsoft.com/library.</span><span class="sxs-lookup"><span data-stu-id="60d18-111">For more information on using cryptography, see the Cryptography topic in the Platform SDK documentation at http://msdn.microsoft.com/library.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60d18-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60d18-112">See also</span></span>

- [<span data-ttu-id="60d18-113">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="60d18-113">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
