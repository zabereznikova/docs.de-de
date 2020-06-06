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
ms.openlocfilehash: e53f4c5c9e24fb25b43b7f27b80ab984214eeac2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "69927775"
---
# <a name="configuring-cryptography-classes"></a><span data-ttu-id="87003-102">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="87003-102">Configuring Cryptography Classes</span></span>
<span data-ttu-id="87003-103">Der Windows SDK ermöglicht es Computer Administratoren, die standardmäßigen Kryptografiealgorithmen und Algorithmusimplementierungen zu konfigurieren, die von den .NET Framework und entsprechend geschriebenen Anwendungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="87003-103">The Windows SDK allows computer administrators to configure the default cryptographic algorithms and algorithm implementations that the .NET Framework and appropriately written applications use.</span></span>  <span data-ttu-id="87003-104">Beispielsweise kann ein Unternehmen, das über eine eigene Implementierung eines kryptografischen Algorithmus verfügt, diese Implementierung als Standardwert anstelle der in der Windows SDK gelieferten Implementierung festlegen.</span><span class="sxs-lookup"><span data-stu-id="87003-104">For example, an enterprise that has its own implementation of a cryptographic algorithm can make that implementation the default instead of the implementation shipped in the Windows SDK.</span></span> <span data-ttu-id="87003-105">Obwohl verwaltete Anwendungen, die Kryptografie verwenden, immer eine explizite Bindung an eine bestimmte Implementierung treffen können, empfiehlt es sich, kryptografieobjekte mithilfe des kryptografiekonfigurationssystems zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="87003-105">Although managed applications that use cryptography can always choose to explicitly bind to a particular implementation, it is recommended that they create cryptographic objects by using the crypto configuration system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="87003-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="87003-106">In This Section</span></span>  
 [<span data-ttu-id="87003-107">Zuordnen von Algorithmennamen zu kryptografischen Klassen</span><span class="sxs-lookup"><span data-stu-id="87003-107">Mapping Algorithm Names to Cryptography Classes</span></span>](map-algorithm-names-to-cryptography-classes.md)  
 <span data-ttu-id="87003-108">Beschreibt, wie ein Algorithmusname einer Kryptografieklasse zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="87003-108">Describes how to map an algorithm name to a cryptography class.</span></span>  
  
 [<span data-ttu-id="87003-109">Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen</span><span class="sxs-lookup"><span data-stu-id="87003-109">Mapping Object Identifiers to Cryptography Algorithms</span></span>](map-object-identifiers-to-cryptography-algorithms.md)  
 <span data-ttu-id="87003-110">Beschreibt, wie ein Objekt Bezeichner einem Kryptografiealgorithmus zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="87003-110">Describes how to map an object identifier to a cryptography algorithm.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="87003-111">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="87003-111">Related Sections</span></span>  
 [<span data-ttu-id="87003-112">Kryptografiedienste</span><span class="sxs-lookup"><span data-stu-id="87003-112">Cryptographic Services</span></span>](../../standard/security/cryptographic-services.md)  
 <span data-ttu-id="87003-113">Bietet eine Übersicht über die Kryptografiedienste, die von der Windows SDK bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="87003-113">Provides an overview of cryptographic services provided by the Windows SDK.</span></span>  
  
 [<span data-ttu-id="87003-114">Schema für Kryptografieeinstellungen</span><span class="sxs-lookup"><span data-stu-id="87003-114">Cryptography Settings Schema</span></span>](./file-schema/cryptography/index.md)  
 <span data-ttu-id="87003-115">Beschreibt die Elemente, mit denen angezeigte Algorithmusnamen Klassen zugeordnet werden, die Kryptografiealgorithmen implementieren.</span><span class="sxs-lookup"><span data-stu-id="87003-115">Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>
