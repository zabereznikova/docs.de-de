---
title: IMetaDataConverter-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataConverter
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataConverter
helpviewer_keywords: IMetaDataConverter interface [.NET Framework metadata]
ms.assetid: 9caea662-0167-4267-b14a-2fa42c3be4ea
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f551a774a860f595cc90a7cca9eee2c726ef50ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataconverter-interface"></a><span data-ttu-id="bc5af-102">IMetaDataConverter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bc5af-102">IMetaDataConverter Interface</span></span>
<span data-ttu-id="bc5af-103">Stellt Methoden zum Zuordnen von Typbibliotheken zu ihren Metadatensignaturen sowie zum gegenseitigen Konvertieren bereit.</span><span class="sxs-lookup"><span data-stu-id="bc5af-103">Provides methods to map type libraries to their metadata signatures, and to convert from one to the other.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bc5af-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="bc5af-104">Methods</span></span>  
  
|<span data-ttu-id="bc5af-105">Methode</span><span class="sxs-lookup"><span data-stu-id="bc5af-105">Method</span></span>|<span data-ttu-id="bc5af-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bc5af-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bc5af-107">GetMetaDataFromTypeInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="bc5af-107">GetMetaDataFromTypeInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypeinfo-method.md)|<span data-ttu-id="bc5af-108">Ruft einen Zeiger auf eine [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) Instanz, die die Metadatensignatur der Typbibliothek, auf die verwiesen wird durch das angegebene steht `ITypeInfo` Instanz.</span><span class="sxs-lookup"><span data-stu-id="bc5af-108">Gets a pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature for the type library referenced by the specified `ITypeInfo` instance.</span></span>|  
|[<span data-ttu-id="bc5af-109">GetMetaDataFromTypeLib-Methode</span><span class="sxs-lookup"><span data-stu-id="bc5af-109">GetMetaDataFromTypeLib Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypelib-method.md)|<span data-ttu-id="bc5af-110">Ruft einen Zeiger auf eine `IMetaDataImport` Instanz, die die Metadatensignatur der Typbibliothek, dargestellt durch das angegebene steht `ITypeLib` Instanz.</span><span class="sxs-lookup"><span data-stu-id="bc5af-110">Gets a pointer to an `IMetaDataImport` instance that represents the metadata signature for the type library represented by the specified `ITypeLib` instance.</span></span>|  
|[<span data-ttu-id="bc5af-111">GetTypeLibFromMetaData-Methode</span><span class="sxs-lookup"><span data-stu-id="bc5af-111">GetTypeLibFromMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-gettypelibfrommetadata-method.md)|<span data-ttu-id="bc5af-112">Ruft einen Zeiger auf eine `ITypeLib` Instanz, die die Typbibliothek darstellt, die die angegebenen Moduls und Bibliothek Namen aufweist.</span><span class="sxs-lookup"><span data-stu-id="bc5af-112">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified module and library names.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bc5af-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bc5af-113">Requirements</span></span>  
 <span data-ttu-id="bc5af-114">**Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc5af-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc5af-115">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bc5af-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bc5af-116">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="bc5af-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bc5af-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc5af-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc5af-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc5af-118">See Also</span></span>  
 [<span data-ttu-id="bc5af-119">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="bc5af-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="bc5af-120">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bc5af-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
