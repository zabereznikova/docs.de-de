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
ms.openlocfilehash: 6717c48fca14f2200f783a984594388ef3b29c15
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62042470"
---
# <a name="imetadataimport2-interface"></a><span data-ttu-id="de270-102">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="de270-102">IMetaDataImport2 Interface</span></span>
<span data-ttu-id="de270-103">Erweitert die [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) Schnittstelle, um die Funktion für die Arbeit mit generischen Typen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="de270-103">Extends the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface to provide the capability of working with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="de270-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="de270-104">Methods</span></span>  
  
|<span data-ttu-id="de270-105">Methode</span><span class="sxs-lookup"><span data-stu-id="de270-105">Method</span></span>|<span data-ttu-id="de270-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="de270-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="de270-107">EnumGenericParamConstraints-Methode</span><span class="sxs-lookup"><span data-stu-id="de270-107">EnumGenericParamConstraints Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparamconstraints-method.md)|<span data-ttu-id="de270-108">Ruft einen Enumerator für ein Array von generischen Parameter-Einschränkungen, die durch das angegebene Token dargestellten generischen Parameter zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="de270-108">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="de270-109">EnumGenericParams-Methode</span><span class="sxs-lookup"><span data-stu-id="de270-109">EnumGenericParams Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md)|<span data-ttu-id="de270-110">Ruft einen Enumerator für ein Array von generischen Parameter-Token mit dem angegebenen TypeDef oder MethodDef verknüpften token.</span><span class="sxs-lookup"><span data-stu-id="de270-110">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>|  
|[<span data-ttu-id="de270-111">EnumMethodSpecs-Methode</span><span class="sxs-lookup"><span data-stu-id="de270-111">EnumMethodSpecs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enummethodspecs-method.md)|<span data-ttu-id="de270-112">Ruft einen Enumerator für ein Array von MethodSpec-Token mit dem angegebenen MethodDef oder MemberRef verknüpften token.</span><span class="sxs-lookup"><span data-stu-id="de270-112">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>|  
|[<span data-ttu-id="de270-113">GetGenericParamConstraintProps-Methode</span><span class="sxs-lookup"><span data-stu-id="de270-113">GetGenericParamConstraintProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamconstraintprops-method.md)|<span data-ttu-id="de270-114">Ruft die Einschränkung des generischen Parameters, durch das Token der angegebenen Einschränkung dargestellt zugeordneten Metadaten ab.</span><span class="sxs-lookup"><span data-stu-id="de270-114">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>|  
|[<span data-ttu-id="de270-115">GetGenericParamProps-Methode</span><span class="sxs-lookup"><span data-stu-id="de270-115">GetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamprops-method.md)|<span data-ttu-id="de270-116">Ruft die Metadaten, die durch das angegebene Token dargestellten generischen Parameter zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="de270-116">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="de270-117">GetMethodSpecProps-Methode</span><span class="sxs-lookup"><span data-stu-id="de270-117">GetMethodSpecProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getmethodspecprops-method.md)|<span data-ttu-id="de270-118">Ruft die Metadatensignatur der Methode verwiesen wird, vom angegebenen MethodSpec token ab.</span><span class="sxs-lookup"><span data-stu-id="de270-118">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>|  
|[<span data-ttu-id="de270-119">GetPEKind-Methode</span><span class="sxs-lookup"><span data-stu-id="de270-119">GetPEKind Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)|<span data-ttu-id="de270-120">Ruft einen Wert, der das Bestimmen der Art des Codes in eine portierbare ausführbare Datei (PE) Datei, in der Regel eine DLL oder EXE-Datei, im aktuellen Metadatenbereich definiert</span><span class="sxs-lookup"><span data-stu-id="de270-120">Gets a value identifying the nature of the code in a portable executable (PE) file, typically a DLL or EXE file, defined in the current metadata scope</span></span>|  
|[<span data-ttu-id="de270-121">GetVersionString-Methode</span><span class="sxs-lookup"><span data-stu-id="de270-121">GetVersionString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getversionstring-method.md)|<span data-ttu-id="de270-122">Ruft die Version der Laufzeit, die verwendet wurde, zur Erstellung der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="de270-122">Gets the version number of the runtime that was used to build the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="de270-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="de270-123">Requirements</span></span>  
 <span data-ttu-id="de270-124">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de270-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de270-125">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="de270-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="de270-126">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="de270-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="de270-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de270-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de270-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de270-128">See also</span></span>

- <xref:System.Reflection.PortableExecutableKinds>
- [<span data-ttu-id="de270-129">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="de270-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="de270-130">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="de270-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
