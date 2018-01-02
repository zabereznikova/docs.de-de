---
title: Konfigurieren kryptografischer Klassen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuration files [.NET Framework], cryptography
- cryptographic algorithms
- security [.NET Framework], encryption
- cryptography, classes
- .NET Framework application configuration, cryptography
- default cryptography
ms.assetid: eee3ccb8-2c0d-4f35-b38d-6892a46c14e5
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 23bd6007beb870895316a565283ee7e7354c931b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="configuring-cryptography-classes"></a><span data-ttu-id="a2ef0-102">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="a2ef0-102">Configuring Cryptography Classes</span></span>
<span data-ttu-id="a2ef0-103">Die [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] Computeradministratoren so konfigurieren Sie die standardmäßige kryptografische Algorithmen und Algorithmus-Implementierungen, die .NET Framework und entsprechend geschriebene Anwendungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a2ef0-103">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] allows computer administrators to configure the default cryptographic algorithms and algorithm implementations that the .NET Framework and appropriately written applications use.</span></span>  <span data-ttu-id="a2ef0-104">Beispielsweise ein Unternehmen, das über eine eigene Implementierung eines kryptografischen Algorithmus kann als, dass diese Implementierung standardanwendung anstelle der Implementierung, die im Lieferumfang der [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a2ef0-104">For example, an enterprise that has its own implementation of a cryptographic algorithm can make that implementation the default instead of the implementation shipped in the [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span></span> <span data-ttu-id="a2ef0-105">Zwar verwaltete Anwendungen, die Kryptografie verwenden immer auswählen können, um explizit an eine bestimmte Implementierung zu binden, wird empfohlen, sie kryptografische Objekte mithilfe der CryptoAPI Konfigurationssystem erstellen.</span><span class="sxs-lookup"><span data-stu-id="a2ef0-105">Although managed applications that use cryptography can always choose to explicitly bind to a particular implementation, it is recommended that they create cryptographic objects by using the crypto configuration system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a2ef0-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a2ef0-106">In This Section</span></span>  
 [<span data-ttu-id="a2ef0-107">Zuordnen von Algorithmennamen zu kryptografischen Klassen</span><span class="sxs-lookup"><span data-stu-id="a2ef0-107">Mapping Algorithm Names to Cryptography Classes</span></span>](../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)  
 <span data-ttu-id="a2ef0-108">Beschreibt das Zuordnen ein Algorithmusnamens zu einer kryptografischen Klasse.</span><span class="sxs-lookup"><span data-stu-id="a2ef0-108">Describes how to map an algorithm name to a cryptography class.</span></span>  
  
 [<span data-ttu-id="a2ef0-109">Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen</span><span class="sxs-lookup"><span data-stu-id="a2ef0-109">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)  
 <span data-ttu-id="a2ef0-110">Beschreibt, wie der Bezeichner eines Objekts zu einem kryptografischen Algorithmus zuordnen.</span><span class="sxs-lookup"><span data-stu-id="a2ef0-110">Describes how to map an object identifier to a cryptography algorithm.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a2ef0-111">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="a2ef0-111">Related Sections</span></span>  
 [<span data-ttu-id="a2ef0-112">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="a2ef0-112">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)  
 <span data-ttu-id="a2ef0-113">Bietet eine Übersicht über kryptografische Dienste von der [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a2ef0-113">Provides an overview of cryptographic services provided by the [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span></span>  
  
 [<span data-ttu-id="a2ef0-114">Cryptography Settings Schema (Schema für Kryptografieeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="a2ef0-114">Cryptography Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 <span data-ttu-id="a2ef0-115">Beschreibt die Elemente, mit denen angezeigte Algorithmusnamen Klassen zugeordnet werden, die Kryptografiealgorithmen implementieren.</span><span class="sxs-lookup"><span data-stu-id="a2ef0-115">Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>
