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
ms.openlocfilehash: 5d12aae31ec78f80bea7df1bb0f37ac78dc37de2
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105069"
---
# <a name="configuring-cryptography-classes"></a><span data-ttu-id="60167-103">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="60167-103">Configuring Cryptography Classes</span></span>
<span data-ttu-id="60167-104">Der Windows SDK ermöglicht es Computer Administratoren, die standardmäßigen Kryptografiealgorithmen und Algorithmusimplementierungen zu konfigurieren, die von den .NET Framework und entsprechend geschriebenen Anwendungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="60167-104">The Windows SDK allows computer administrators to configure the default cryptographic algorithms and algorithm implementations that the .NET Framework and appropriately written applications use.</span></span>  <span data-ttu-id="60167-105">Beispielsweise kann ein Unternehmen, das über eine eigene Implementierung eines kryptografischen Algorithmus verfügt, diese Implementierung als Standardwert anstelle der in der Windows SDK gelieferten Implementierung festlegen.</span><span class="sxs-lookup"><span data-stu-id="60167-105">For example, an enterprise that has its own implementation of a cryptographic algorithm can make that implementation the default instead of the implementation shipped in the Windows SDK.</span></span> <span data-ttu-id="60167-106">Obwohl verwaltete Anwendungen, die Kryptografie verwenden, immer eine explizite Bindung an eine bestimmte Implementierung treffen können, empfiehlt es sich, kryptografieobjekte mithilfe des kryptografiekonfigurationssystems zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="60167-106">Although managed applications that use cryptography can always choose to explicitly bind to a particular implementation, it is recommended that they create cryptographic objects by using the crypto configuration system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="60167-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="60167-107">In This Section</span></span>  
 [<span data-ttu-id="60167-108">Zuordnen von Algorithmennamen zu kryptografischen Klassen</span><span class="sxs-lookup"><span data-stu-id="60167-108">Mapping Algorithm Names to Cryptography Classes</span></span>](map-algorithm-names-to-cryptography-classes.md)  
 <span data-ttu-id="60167-109">Beschreibt, wie ein Algorithmusname einer Kryptografieklasse zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="60167-109">Describes how to map an algorithm name to a cryptography class.</span></span>  
  
 [<span data-ttu-id="60167-110">Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen</span><span class="sxs-lookup"><span data-stu-id="60167-110">Mapping Object Identifiers to Cryptography Algorithms</span></span>](map-object-identifiers-to-cryptography-algorithms.md)  
 <span data-ttu-id="60167-111">Beschreibt, wie ein Objekt Bezeichner einem Kryptografiealgorithmus zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="60167-111">Describes how to map an object identifier to a cryptography algorithm.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="60167-112">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="60167-112">Related Sections</span></span>  
 [<span data-ttu-id="60167-113">Kryptografiedienste</span><span class="sxs-lookup"><span data-stu-id="60167-113">Cryptographic Services</span></span>](../../standard/security/cryptographic-services.md)  
 <span data-ttu-id="60167-114">Bietet eine Übersicht über die Kryptografiedienste, die von der Windows SDK bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="60167-114">Provides an overview of cryptographic services provided by the Windows SDK.</span></span>  
  
 [<span data-ttu-id="60167-115">Schema für Kryptografieeinstellungen</span><span class="sxs-lookup"><span data-stu-id="60167-115">Cryptography Settings Schema</span></span>](./file-schema/cryptography/index.md)  
 <span data-ttu-id="60167-116">Beschreibt die Elemente, mit denen angezeigte Algorithmusnamen Klassen zugeordnet werden, die Kryptografiealgorithmen implementieren.</span><span class="sxs-lookup"><span data-stu-id="60167-116">Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>
