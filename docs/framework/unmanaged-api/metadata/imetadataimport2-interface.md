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
ms.openlocfilehash: fe9e87618291218a41e52f80198ce9068c9c56e2
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490393"
---
# <a name="imetadataimport2-interface"></a><span data-ttu-id="fc57e-102">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fc57e-102">IMetaDataImport2 Interface</span></span>
<span data-ttu-id="fc57e-103">Erweitert die [IMetaDataImport](imetadataimport-interface.md) -Schnittstelle, um die Funktion zum Arbeiten mit generischen Typen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="fc57e-103">Extends the [IMetaDataImport](imetadataimport-interface.md) interface to provide the capability of working with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fc57e-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="fc57e-104">Methods</span></span>  
  
|<span data-ttu-id="fc57e-105">Methode</span><span class="sxs-lookup"><span data-stu-id="fc57e-105">Method</span></span>|<span data-ttu-id="fc57e-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fc57e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fc57e-107">EnumGenericParamConstraints-Methode</span><span class="sxs-lookup"><span data-stu-id="fc57e-107">EnumGenericParamConstraints Method</span></span>](imetadataimport2-enumgenericparamconstraints-method.md)|<span data-ttu-id="fc57e-108">Ruft einen Enumerator für ein Array von generischen Parameter Einschränkungen ab, die dem generischen Parameter zugeordnet sind, der durch das angegebene Token dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="fc57e-108">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="fc57e-109">EnumGenericParams-Methode</span><span class="sxs-lookup"><span data-stu-id="fc57e-109">EnumGenericParams Method</span></span>](imetadataimport2-enumgenericparams-method.md)|<span data-ttu-id="fc57e-110">Ruft einen Enumerator für ein Array von generischen Parameter Token ab, die dem angegebenen TypeDef-oder MethodDef-Token zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="fc57e-110">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>|  
|[<span data-ttu-id="fc57e-111">EnumMethodSpecs-Methode</span><span class="sxs-lookup"><span data-stu-id="fc57e-111">EnumMethodSpecs Method</span></span>](imetadataimport2-enummethodspecs-method.md)|<span data-ttu-id="fc57e-112">Ruft einen Enumerator für ein Array von MethodSpec-Token ab, das mit dem angegebenen MethodDef-oder mitgliedsverweistoken verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="fc57e-112">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>|  
|[<span data-ttu-id="fc57e-113">GetGenericParamConstraintProps-Methode</span><span class="sxs-lookup"><span data-stu-id="fc57e-113">GetGenericParamConstraintProps Method</span></span>](imetadataimport2-getgenericparamconstraintprops-method.md)|<span data-ttu-id="fc57e-114">Ruft die Metadaten ab, die der durch das angegebene Einschränkungs Token dargestellten generischen Parameter Einschränkung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="fc57e-114">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>|  
|[<span data-ttu-id="fc57e-115">GetGenericParamProps-Methode</span><span class="sxs-lookup"><span data-stu-id="fc57e-115">GetGenericParamProps Method</span></span>](imetadataimport2-getgenericparamprops-method.md)|<span data-ttu-id="fc57e-116">Ruft die Metadaten ab, die dem durch das angegebene Token dargestellten generischen Parameter zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="fc57e-116">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="fc57e-117">GetMethodSpecProps-Methode</span><span class="sxs-lookup"><span data-stu-id="fc57e-117">GetMethodSpecProps Method</span></span>](imetadataimport2-getmethodspecprops-method.md)|<span data-ttu-id="fc57e-118">Ruft die Metadatensignatur der Methode ab, auf die durch das angegebene MethodSpec-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="fc57e-118">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>|  
|[<span data-ttu-id="fc57e-119">GetPEKind-Methode</span><span class="sxs-lookup"><span data-stu-id="fc57e-119">GetPEKind Method</span></span>](imetadataimport2-getpekind-method.md)|<span data-ttu-id="fc57e-120">Ruft einen Wert ab, der die Art des Codes in einer portablen ausführbaren Datei (PE) identifiziert, normalerweise eine DLL-oder exe-Datei, die im aktuellen Metadatenbereich definiert ist.</span><span class="sxs-lookup"><span data-stu-id="fc57e-120">Gets a value identifying the nature of the code in a portable executable (PE) file, typically a DLL or EXE file, defined in the current metadata scope</span></span>|  
|[<span data-ttu-id="fc57e-121">GetVersionString-Methode</span><span class="sxs-lookup"><span data-stu-id="fc57e-121">GetVersionString Method</span></span>](imetadataimport2-getversionstring-method.md)|<span data-ttu-id="fc57e-122">Ruft die Versionsnummer der Laufzeit ab, die zum Erstellen der Assembly verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="fc57e-122">Gets the version number of the runtime that was used to build the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fc57e-123">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fc57e-123">Requirements</span></span>  
 <span data-ttu-id="fc57e-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc57e-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc57e-125">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fc57e-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fc57e-126">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="fc57e-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fc57e-127">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc57e-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc57e-128">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="fc57e-128">See also</span></span>

- <xref:System.Reflection.PortableExecutableKinds>
- [<span data-ttu-id="fc57e-129">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="fc57e-129">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="fc57e-130">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fc57e-130">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
