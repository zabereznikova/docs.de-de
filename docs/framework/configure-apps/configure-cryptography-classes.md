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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705531"
---
# <a name="configuring-cryptography-classes"></a><span data-ttu-id="76d64-102">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="76d64-102">Configuring Cryptography Classes</span></span>
<span data-ttu-id="76d64-103">Die [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] Computeradministratoren so konfigurieren Sie die standardmäßigen kryptoalgorithmen und algorithmusimplementierungen, die .NET Framework und entsprechend geschriebene Anwendungen verwenden, können.</span><span class="sxs-lookup"><span data-stu-id="76d64-103">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] allows computer administrators to configure the default cryptographic algorithms and algorithm implementations that the .NET Framework and appropriately written applications use.</span></span>  <span data-ttu-id="76d64-104">Z. B. ein Unternehmen, die eine eigene Implementierung des ein kryptografischer Algorithmus möglich, dass diese Implementierung standardmäßig anstelle der Implementierung, die im Lieferumfang von der [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76d64-104">For example, an enterprise that has its own implementation of a cryptographic algorithm can make that implementation the default instead of the implementation shipped in the [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span></span> <span data-ttu-id="76d64-105">Obwohl es sich bei verwaltete Anwendungen, mit denen Kryptografie immer explizit an eine bestimmte Implementierung gebunden auswählen können, empfiehlt es sich, dass sie kryptografische Objekte mithilfe von kryptografischen Konfigurationssystem erstellen.</span><span class="sxs-lookup"><span data-stu-id="76d64-105">Although managed applications that use cryptography can always choose to explicitly bind to a particular implementation, it is recommended that they create cryptographic objects by using the crypto configuration system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="76d64-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="76d64-106">In This Section</span></span>  
 [<span data-ttu-id="76d64-107">Zuordnen von Algorithmennamen zu kryptografischen Klassen</span><span class="sxs-lookup"><span data-stu-id="76d64-107">Mapping Algorithm Names to Cryptography Classes</span></span>](../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)  
 <span data-ttu-id="76d64-108">Beschreibt, wie ein Algorithmusnamens zu einer kryptografischen Klasse zuordnen.</span><span class="sxs-lookup"><span data-stu-id="76d64-108">Describes how to map an algorithm name to a cryptography class.</span></span>  
  
 [<span data-ttu-id="76d64-109">Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen</span><span class="sxs-lookup"><span data-stu-id="76d64-109">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)  
 <span data-ttu-id="76d64-110">Beschreibt, wie eine Objekt-ID zu einem kryptografischen Algorithmus zuordnen.</span><span class="sxs-lookup"><span data-stu-id="76d64-110">Describes how to map an object identifier to a cryptography algorithm.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="76d64-111">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="76d64-111">Related Sections</span></span>  
 [<span data-ttu-id="76d64-112">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="76d64-112">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)  
 <span data-ttu-id="76d64-113">Bietet eine Übersicht über kryptografische Dienste von der [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76d64-113">Provides an overview of cryptographic services provided by the [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span></span>  
  
 [<span data-ttu-id="76d64-114">Cryptography Settings Schema (Schema für Kryptografieeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="76d64-114">Cryptography Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 <span data-ttu-id="76d64-115">Beschreibt die Elemente, mit denen angezeigte Algorithmusnamen Klassen zugeordnet werden, die Kryptografiealgorithmen implementieren.</span><span class="sxs-lookup"><span data-stu-id="76d64-115">Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>
