---
title: Konfigurieren kryptografischer Klassen
ms.date: 03/30/2017
helpviewer_keywords:
- configuration files [.NET Framework], cryptography
- cryptographic algorithms
- security [.NET Framework], encryption
- cryptography, classes
- .NET Framework application configuration, cryptography
- default cryptography
ms.assetid: eee3ccb8-2c0d-4f35-b38d-6892a46c14e5
ms.openlocfilehash: ba11eed316e227ceae4cb5acecb2b081fa8868f2
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2019
ms.locfileid: "55084405"
---
# <a name="configuring-cryptography-classes"></a><span data-ttu-id="8c36e-102">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="8c36e-102">Configuring Cryptography Classes</span></span>
<span data-ttu-id="8c36e-103">Die [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] Computeradministratoren so konfigurieren Sie die standardmäßigen kryptoalgorithmen und algorithmusimplementierungen, die .NET Framework und entsprechend geschriebene Anwendungen verwenden, können.</span><span class="sxs-lookup"><span data-stu-id="8c36e-103">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] allows computer administrators to configure the default cryptographic algorithms and algorithm implementations that the .NET Framework and appropriately written applications use.</span></span>  <span data-ttu-id="8c36e-104">Z. B. ein Unternehmen, die eine eigene Implementierung des ein kryptografischer Algorithmus möglich, dass diese Implementierung standardmäßig anstelle der Implementierung, die im Lieferumfang von der [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c36e-104">For example, an enterprise that has its own implementation of a cryptographic algorithm can make that implementation the default instead of the implementation shipped in the [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span></span> <span data-ttu-id="8c36e-105">Obwohl es sich bei verwaltete Anwendungen, mit denen Kryptografie immer explizit an eine bestimmte Implementierung gebunden auswählen können, empfiehlt es sich, dass sie kryptografische Objekte mithilfe von kryptografischen Konfigurationssystem erstellen.</span><span class="sxs-lookup"><span data-stu-id="8c36e-105">Although managed applications that use cryptography can always choose to explicitly bind to a particular implementation, it is recommended that they create cryptographic objects by using the crypto configuration system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8c36e-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8c36e-106">In This Section</span></span>  
 [<span data-ttu-id="8c36e-107">Zuordnen von Algorithmennamen zu kryptografischen Klassen</span><span class="sxs-lookup"><span data-stu-id="8c36e-107">Mapping Algorithm Names to Cryptography Classes</span></span>](../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)  
 <span data-ttu-id="8c36e-108">Beschreibt, wie ein Algorithmusnamens zu einer kryptografischen Klasse zuordnen.</span><span class="sxs-lookup"><span data-stu-id="8c36e-108">Describes how to map an algorithm name to a cryptography class.</span></span>  
  
 [<span data-ttu-id="8c36e-109">Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen</span><span class="sxs-lookup"><span data-stu-id="8c36e-109">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)  
 <span data-ttu-id="8c36e-110">Beschreibt, wie eine Objekt-ID zu einem kryptografischen Algorithmus zuordnen.</span><span class="sxs-lookup"><span data-stu-id="8c36e-110">Describes how to map an object identifier to a cryptography algorithm.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8c36e-111">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="8c36e-111">Related Sections</span></span>  
 [<span data-ttu-id="8c36e-112">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="8c36e-112">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)  
 <span data-ttu-id="8c36e-113">Bietet eine Übersicht über kryptografische Dienste von der [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c36e-113">Provides an overview of cryptographic services provided by the [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span></span>  
  
 [<span data-ttu-id="8c36e-114">Cryptography Settings Schema (Schema für Kryptografieeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="8c36e-114">Cryptography Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 <span data-ttu-id="8c36e-115">Beschreibt die Elemente, mit denen angezeigte Algorithmusnamen Klassen zugeordnet werden, die Kryptografiealgorithmen implementieren.</span><span class="sxs-lookup"><span data-stu-id="8c36e-115">Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>
