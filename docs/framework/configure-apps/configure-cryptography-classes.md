---
title: Konfigurieren kryptografischer Klassen
description: Erfahren Sie, wie Computer Administratoren die standardmäßigen Kryptografiealgorithmen und Algorithmusimplementierungen konfigurieren können, die von .net und Anwendungen verwendet werden.
ms.date: 03/30/2017
helpviewer_keywords:
- configuration files [.NET Framework], cryptography
- cryptographic algorithms
- security [.NET Framework], encryption
- cryptography, classes
- .NET Framework application configuration, cryptography
- default cryptography
ms.assetid: eee3ccb8-2c0d-4f35-b38d-6892a46c14e5
ms.openlocfilehash: 5262dfca914fd5306297ea9535bcef3d2088d107
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91165207"
---
# <a name="configuring-cryptography-classes"></a><span data-ttu-id="df23a-103">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="df23a-103">Configuring Cryptography Classes</span></span>

<span data-ttu-id="df23a-104">Der Windows SDK ermöglicht es Computer Administratoren, die standardmäßigen Kryptografiealgorithmen und Algorithmusimplementierungen zu konfigurieren, die von den .NET Framework und entsprechend geschriebenen Anwendungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="df23a-104">The Windows SDK allows computer administrators to configure the default cryptographic algorithms and algorithm implementations that the .NET Framework and appropriately written applications use.</span></span>  <span data-ttu-id="df23a-105">Beispielsweise kann ein Unternehmen, das über eine eigene Implementierung eines kryptografischen Algorithmus verfügt, diese Implementierung als Standardwert anstelle der in der Windows SDK gelieferten Implementierung festlegen.</span><span class="sxs-lookup"><span data-stu-id="df23a-105">For example, an enterprise that has its own implementation of a cryptographic algorithm can make that implementation the default instead of the implementation shipped in the Windows SDK.</span></span> <span data-ttu-id="df23a-106">Obwohl verwaltete Anwendungen, die Kryptografie verwenden, immer eine explizite Bindung an eine bestimmte Implementierung treffen können, empfiehlt es sich, kryptografieobjekte mithilfe des kryptografiekonfigurationssystems zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="df23a-106">Although managed applications that use cryptography can always choose to explicitly bind to a particular implementation, it is recommended that they create cryptographic objects by using the crypto configuration system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="df23a-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="df23a-107">In This Section</span></span>  

 [<span data-ttu-id="df23a-108">Zuordnen von Algorithmennamen zu kryptografischen Klassen</span><span class="sxs-lookup"><span data-stu-id="df23a-108">Mapping Algorithm Names to Cryptography Classes</span></span>](map-algorithm-names-to-cryptography-classes.md)  
 <span data-ttu-id="df23a-109">Beschreibt, wie ein Algorithmusname einer Kryptografieklasse zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="df23a-109">Describes how to map an algorithm name to a cryptography class.</span></span>  
  
 [<span data-ttu-id="df23a-110">Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen</span><span class="sxs-lookup"><span data-stu-id="df23a-110">Mapping Object Identifiers to Cryptography Algorithms</span></span>](map-object-identifiers-to-cryptography-algorithms.md)  
 <span data-ttu-id="df23a-111">Beschreibt, wie ein Objekt Bezeichner einem Kryptografiealgorithmus zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="df23a-111">Describes how to map an object identifier to a cryptography algorithm.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="df23a-112">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="df23a-112">Related Sections</span></span>  

 [<span data-ttu-id="df23a-113">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="df23a-113">Cryptographic Services</span></span>](../../standard/security/cryptographic-services.md)  
 <span data-ttu-id="df23a-114">Bietet eine Übersicht über die Kryptografiedienste, die von der Windows SDK bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="df23a-114">Provides an overview of cryptographic services provided by the Windows SDK.</span></span>  
  
 [<span data-ttu-id="df23a-115">Schema für Kryptografieeinstellungen</span><span class="sxs-lookup"><span data-stu-id="df23a-115">Cryptography Settings Schema</span></span>](./file-schema/cryptography/index.md)  
 <span data-ttu-id="df23a-116">Beschreibt die Elemente, mit denen angezeigte Algorithmusnamen Klassen zugeordnet werden, die Kryptografiealgorithmen implementieren.</span><span class="sxs-lookup"><span data-stu-id="df23a-116">Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>
