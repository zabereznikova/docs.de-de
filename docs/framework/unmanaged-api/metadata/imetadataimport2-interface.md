---
title: IMetaDataImport2-Schnittstelle
ms.date: 03/30/2017
api_name:
- IMetaDataImport2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2
helpviewer_keywords:
- IMetaDataImport2 interface [.NET Framework metadata]
ms.assetid: d39b2b87-ba53-4771-ae53-952a68452511
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1328e40c74c17c55cc476bba761c1c3be9af034e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449337"
---
# <a name="imetadataimport2-interface"></a><span data-ttu-id="a24c1-102">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a24c1-102">IMetaDataImport2 Interface</span></span>
<span data-ttu-id="a24c1-103">Erweitert die [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) Schnittstelle, um die Funktion der Arbeit mit generischen Typen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="a24c1-103">Extends the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface to provide the capability of working with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a24c1-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="a24c1-104">Methods</span></span>  
  
|<span data-ttu-id="a24c1-105">Methode</span><span class="sxs-lookup"><span data-stu-id="a24c1-105">Method</span></span>|<span data-ttu-id="a24c1-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a24c1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a24c1-107">EnumGenericParamConstraints-Methode</span><span class="sxs-lookup"><span data-stu-id="a24c1-107">EnumGenericParamConstraints Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparamconstraints-method.md)|<span data-ttu-id="a24c1-108">Ruft einen Enumerator für ein Array mit Einschränkungen für generische Typparameter durch das angegebene Token dargestellten generischen Parameter zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="a24c1-108">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="a24c1-109">EnumGenericParams-Methode</span><span class="sxs-lookup"><span data-stu-id="a24c1-109">EnumGenericParams Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md)|<span data-ttu-id="a24c1-110">Ruft einen Enumerator für ein Array von generischen Parameter-Token mit dem angegebenen TypeDef- oder MethodDef verknüpften token.</span><span class="sxs-lookup"><span data-stu-id="a24c1-110">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>|  
|[<span data-ttu-id="a24c1-111">EnumMethodSpecs-Methode</span><span class="sxs-lookup"><span data-stu-id="a24c1-111">EnumMethodSpecs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enummethodspecs-method.md)|<span data-ttu-id="a24c1-112">Ruft einen Enumerator für ein Array von MethodSpec-Token mit der angegebenen MethodDef oder MemberRef token.</span><span class="sxs-lookup"><span data-stu-id="a24c1-112">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>|  
|[<span data-ttu-id="a24c1-113">GetGenericParamConstraintProps-Methode</span><span class="sxs-lookup"><span data-stu-id="a24c1-113">GetGenericParamConstraintProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamconstraintprops-method.md)|<span data-ttu-id="a24c1-114">Ruft die Einschränkung des generischen Parameters, durch die angegebene Einschränkung-Token dargestellt wird zugeordneten Metadaten ab.</span><span class="sxs-lookup"><span data-stu-id="a24c1-114">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>|  
|[<span data-ttu-id="a24c1-115">GetGenericParamProps-Methode</span><span class="sxs-lookup"><span data-stu-id="a24c1-115">GetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamprops-method.md)|<span data-ttu-id="a24c1-116">Ruft die Metadaten, die durch das angegebene Token dargestellten generischen Parameter zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="a24c1-116">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="a24c1-117">GetMethodSpecProps-Methode</span><span class="sxs-lookup"><span data-stu-id="a24c1-117">GetMethodSpecProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getmethodspecprops-method.md)|<span data-ttu-id="a24c1-118">Ruft die Metadatensignatur der Methode verwiesen wird, vom angegebenen MethodSpec-token ab.</span><span class="sxs-lookup"><span data-stu-id="a24c1-118">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>|  
|[<span data-ttu-id="a24c1-119">GetPEKind-Methode</span><span class="sxs-lookup"><span data-stu-id="a24c1-119">GetPEKind Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)|<span data-ttu-id="a24c1-120">Ruft einen Wert, der die Art des Codes in einer portablen ausführbaren Datei (PE) kennzeichnen Datei, in der Regel eine DLL oder EXE-Datei, im aktuellen Metadatenbereich definiert</span><span class="sxs-lookup"><span data-stu-id="a24c1-120">Gets a value identifying the nature of the code in a portable executable (PE) file, typically a DLL or EXE file, defined in the current metadata scope</span></span>|  
|[<span data-ttu-id="a24c1-121">GetVersionString-Methode</span><span class="sxs-lookup"><span data-stu-id="a24c1-121">GetVersionString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getversionstring-method.md)|<span data-ttu-id="a24c1-122">Ruft die Version der Laufzeit, die verwendet wurde, zum Erstellen der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="a24c1-122">Gets the version number of the runtime that was used to build the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a24c1-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a24c1-123">Requirements</span></span>  
 <span data-ttu-id="a24c1-124">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a24c1-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a24c1-125">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a24c1-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a24c1-126">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="a24c1-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a24c1-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a24c1-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a24c1-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a24c1-128">See Also</span></span>  
 <xref:System.Reflection.PortableExecutableKinds>  
 [<span data-ttu-id="a24c1-129">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="a24c1-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="a24c1-130">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a24c1-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
