---
title: IDENTITY_ATTRIBUTE_BLOB-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: IDENTITY_ATTRIBUTE_BLOB
api_location: fusion.dll
api_type: COM
f1_keywords: IDENTITY_ATTRIBUTE_BLOB
helpviewer_keywords: IDENTITY_ATTRIBUTE_BLOB structure [.NET Framework fusion]
ms.assetid: af14ae5f-d226-47dd-ba90-8fc6e6605d4d
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8b6d732f94eaa1e6988273d947ec924acf7b2521
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="identityattributeblob-structure"></a><span data-ttu-id="cf9f3-102">IDENTITY_ATTRIBUTE_BLOB-Struktur</span><span class="sxs-lookup"><span data-stu-id="cf9f3-102">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>
<span data-ttu-id="cf9f3-103">Enthält Informationen über ein einzelnes Attribut in einer Assembly und besteht aus drei `DWORD`s.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-103">Contains information about a single attribute in an assembly, and consists of three `DWORD`s.</span></span> <span data-ttu-id="cf9f3-104">Jede `DWORD` ist ein Offset in einen Zeichenpuffer von erzeugt der `CurrentIntoBuffer` Methode der [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cf9f3-104">Each `DWORD` is an offset into a character buffer produced by the `CurrentIntoBuffer` method of the [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) interface</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf9f3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="cf9f3-105">Syntax</span></span>  
  
```  
typedef struct _IDENTITY_ATTRIBUTE_BLOB {  
    DWORD  ofsNamespace;  
    DWORD  ofsName;  
    DWORD  ofsValue;  
}   IDENTITY_ATTRIBUTE_BLOB;  
```  
  
## <a name="members"></a><span data-ttu-id="cf9f3-106">Member</span><span class="sxs-lookup"><span data-stu-id="cf9f3-106">Members</span></span>  
  
|<span data-ttu-id="cf9f3-107">Member</span><span class="sxs-lookup"><span data-stu-id="cf9f3-107">Member</span></span>|<span data-ttu-id="cf9f3-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cf9f3-108">Description</span></span>|  
|------------|-----------------|  
|`ofsNamespace`|<span data-ttu-id="cf9f3-109">Der erste Offset in der Zeichenpuffer.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-109">The first offset into the character buffer.</span></span> <span data-ttu-id="cf9f3-110">Dieser Offset ist nicht durch den Namespace für das Attribut jedoch durch eine Reihe von Null-Zeichen folgt.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-110">This offset is not followed by the attribute's namespace, but by a series of null characters.</span></span> <span data-ttu-id="cf9f3-111">Aus diesem Grund ist es nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-111">Therefore, it is not used.</span></span>|  
|`ofsName`|<span data-ttu-id="cf9f3-112">Der zweite Offset in der Zeichenpuffer.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-112">The second offset into the character buffer.</span></span> <span data-ttu-id="cf9f3-113">Dieser Speicherort kennzeichnet den Beginn der den Namen des Attributs.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-113">This location marks the start of the attribute's name.</span></span>|  
|`ofsValue`|<span data-ttu-id="cf9f3-114">Der dritte Offset in der Zeichenpuffer.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-114">The third offset into the character buffer.</span></span> <span data-ttu-id="cf9f3-115">Dieser Speicherort kennzeichnet den Beginn der Wert des Attributs.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-115">This location marks the start of the attribute's value.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="cf9f3-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cf9f3-116">Sample</span></span>  
 <span data-ttu-id="cf9f3-117">Das folgende Beispiel veranschaulicht mehrere grundlegende Schritte, die schließlich ein aufgefülltes führen `IDENTITY_ATTRIBUTE_BLOB` Struktur:</span><span class="sxs-lookup"><span data-stu-id="cf9f3-117">The following example illustrates several basic steps, which eventually result in a populated `IDENTITY_ATTRIBUTE_BLOB` structure:</span></span>  
  
1.  <span data-ttu-id="cf9f3-118">Abrufen einer [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) für die Assembly.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-118">Obtain an [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) for the assembly.</span></span>  
  
2.  <span data-ttu-id="cf9f3-119">Rufen Sie die `IReferenceIdentity::EnumAttributes` -Methode, und rufen eine [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md).</span><span class="sxs-lookup"><span data-stu-id="cf9f3-119">Call the `IReferenceIdentity::EnumAttributes` method, and obtain an [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md).</span></span>  
  
3.  <span data-ttu-id="cf9f3-120">Erstellen Sie einen Zeichenpuffer, und wandeln Sie es als ein `IDENTITY_ATTRIBUTE_BLOB` Struktur.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-120">Create a character buffer, and cast it as an `IDENTITY_ATTRIBUTE_BLOB` structure.</span></span>  
  
4.  <span data-ttu-id="cf9f3-121">Rufen Sie die `CurrentIntoBuffer` Methode der `IEnumIDENTITY_ATTRIBUTE` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-121">Call the `CurrentIntoBuffer` method of the `IEnumIDENTITY_ATTRIBUTE` interface.</span></span> <span data-ttu-id="cf9f3-122">Diese Methode kopiert die Attribute `Namespace`, `Name`, und `Value` in der Zeichenpuffer.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-122">This method copies the attributes `Namespace`, `Name`, and `Value` into the character buffer.</span></span> <span data-ttu-id="cf9f3-123">Die drei Offsets zu diesen Zeichenfolgen zur Verfügung gestellt, in der `IDENTITY_ATTRIBUTE_BLOB` Struktur.</span><span class="sxs-lookup"><span data-stu-id="cf9f3-123">The three offsets to those strings will become available in the `IDENTITY_ATTRIBUTE_BLOB` structure.</span></span>  
  
```  
// EnumAssemblyAttributes.cpp : main project file.  
  
#include "stdafx.h"  
  
#include "fusion.h"  
#include "windows.h"  
#include "stdio.h"  
#include "mscoree.h"  
#include "isolation.h"  
  
typedef HRESULT (__stdcall *PFNGETREF)(LPCWSTR pwzFile, REFIID riid, IUnknown **ppUnk);  
typedef HRESULT (__stdcall *PFNGETAUTH)(IIdentityAuthority **ppIIdentityAuthority);  
  
PFNGETREF                   g_pfnGetAssemblyIdentityFromFile = NULL;  
PFNGETAUTH                  g_pfnGetIdentityAuthority = NULL;  
IUnknown                    *g_pUnk = NULL;  
  
bool Init()  
{  
    HRESULT     hr = S_OK;  
    DWORD       dwSize = 0;  
    bool        bRC = false;  
  
    hr = CorBindToRuntimeEx(NULL, L"wks", 0, CLSID_CorRuntimeHost,  
                           IID_ICorRuntimeHost, (void **)&g_pUnk);  
    if(FAILED(hr)) {  
        printf("Error: Failed to initialize CLR runtime! hr = 0x%0x\n",  
                hr);  
        goto Exit;  
    }  
  
    if (SUCCEEDED(hr)) {  
        hr = GetRealProcAddress("GetAssemblyIdentityFromFile",  
                         (VOID **)&g_pfnGetAssemblyIdentityFromFile);  
    }  
  
    if (SUCCEEDED(hr)) {  
        hr = GetRealProcAddress("GetIdentityAuthority",  
                                (VOID **)&g_pfnGetIdentityAuthority);  
    }  
  
    if (!g_pfnGetAssemblyIdentityFromFile ||   
        !g_pfnGetIdentityAuthority)  
    {  
        printf("Error: Cannot get required APIs from fusion.dll!\n");  
        goto Exit;  
    }  
  
    bRC = true;  
  
Exit:  
    return bRC;  
}  
  
void Shutdown()  
{  
    if(g_pUnk) {  
        g_pUnk->Release();  
        g_pUnk = NULL;  
    }  
}  
  
void Usage()  
{  
    printf("EnumAssemblyAttributes: A tool to enumerate the identity   
            attributes of a given assembly.\n\n");  
    printf("Usage: EnumAssemblyAttributes AssemblyFilePath\n");  
    printf("\n");  
}  
  
int _cdecl wmain(int argc, LPCWSTR argv[])  
{  
    int     iResult = 1;  
    IUnknown                    *pUnk  = NULL;  
    IReferenceIdentity          *pRef  = NULL;  
    HRESULT                     hr     = S_OK;     
    IEnumIDENTITY_ATTRIBUTE     *pEnum = NULL;  
    BYTE                        abData[1024];  
    DWORD                       cbAvailable;  
    DWORD                       cbUsed;  
    IDENTITY_ATTRIBUTE_BLOB     *pBlob;  
  
    if(argc != 2) {  
        Usage();  
        goto Exit;  
    }  
  
    if(!Init()) {  
        printf("Failure initializing EnumIdAttr.\n");  
        goto Exit;  
    }  
  
    hr = g_pfnGetAssemblyIdentityFromFile(argv[1],   
                            __uuidof(IReferenceIdentity), &pUnk);  
  
    if (FAILED(hr)) {  
        printf("GetAssemblyIdentityFromFile failed with hr = 0x%x",   
                hr);  
        goto Exit;  
    }  
  
    hr = pUnk->QueryInterface(__uuidof(IReferenceIdentity),   
                              (void**)&pRef);  
    if (FAILED(hr)) {  
        goto Exit;  
    }  
  
    hr = pRef->EnumAttributes(&pEnum);  
    if (FAILED(hr)) {  
        printf("IReferenceIdentity::EnumAttributes failed with hr =   
                0x%x", hr);  
        goto Exit;  
    }  
  
    pBlob = (IDENTITY_ATTRIBUTE_BLOB *)(abData);  
    while (1) {  
        cbAvailable = sizeof(abData);  
        hr = pEnum->CurrentIntoBuffer(cbAvailable, abData, &cbUsed);  
        if (FAILED(hr)) {  
            printf("IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer failed   
                    with hr = 0x%x", hr);  
            goto Exit;  
        }  
  
        if (! cbUsed) {  
            break;  
        }  
  
        LPWSTR pwzNameSpace = (LPWSTR)(abData + pBlob->ofsNamespace);  
        LPWSTR pwzName      = (LPWSTR)(abData + pBlob->ofsName);  
        LPWSTR pwzValue     = (LPWSTR)(abData + pBlob->ofsValue);  
        printf("%ws: %ws = %ws\n", pwzNameSpace, pwzName, pwzValue);  
  
        hr = pEnum->Skip(1);  
        if (FAILED(hr)) {  
            printf("IEnumIDENTITY_ATTRIBUTE::Skip failed with hr =   
                    0x%x", hr);  
            goto Exit;  
        }  
    }  
  
    iResult = 0;  
  
Exit:  
  
    Shutdown();  
  
    if (pUnk) {  
        pUnk->Release();  
    }  
  
    if (pRef) {  
        pRef->Release();  
    }  
  
    if (pEnum) {  
        pEnum->Release();  
    }  
  
    return iResult;  
}  
```  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="cf9f3-124">So führen Sie das Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="cf9f3-124">To run the sample</span></span>  
 <span data-ttu-id="cf9f3-125">"C:"\\> EnumAssemblyAttributes.exe C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\System.dll</span><span class="sxs-lookup"><span data-stu-id="cf9f3-125">C:\\> EnumAssemblyAttributes.exe C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\System.dll</span></span>  
  
### <a name="sample-output"></a><span data-ttu-id="cf9f3-126">Beispielausgabe:</span><span class="sxs-lookup"><span data-stu-id="cf9f3-126">Sample output</span></span>  
 <span data-ttu-id="cf9f3-127">Culture = Neutral</span><span class="sxs-lookup"><span data-stu-id="cf9f3-127">Culture = neutral</span></span>  
  
 <span data-ttu-id="cf9f3-128">Name = System</span><span class="sxs-lookup"><span data-stu-id="cf9f3-128">name = System</span></span>  
  
 <span data-ttu-id="cf9f3-129">ProcessorArchitecture = MSIL</span><span class="sxs-lookup"><span data-stu-id="cf9f3-129">processorArchitecture = MSIL</span></span>  
  
 <span data-ttu-id="cf9f3-130">PublicKeyToken = b77a5c561934e089</span><span class="sxs-lookup"><span data-stu-id="cf9f3-130">PublicKeyToken = b77a5c561934e089</span></span>  
  
 <span data-ttu-id="cf9f3-131">Version = 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="cf9f3-131">Version = 2.0.0.0</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf9f3-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cf9f3-132">Requirements</span></span>  
 <span data-ttu-id="cf9f3-133">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf9f3-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf9f3-134">**Header:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="cf9f3-134">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="cf9f3-135">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf9f3-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf9f3-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf9f3-136">See Also</span></span>  
 [<span data-ttu-id="cf9f3-137">IReferenceIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cf9f3-137">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)  
 [<span data-ttu-id="cf9f3-138">IEnumIDENTITY_ATTRIBUTE-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cf9f3-138">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)  
 [<span data-ttu-id="cf9f3-139">IDENTITY_ATTRIBUTE-Struktur</span><span class="sxs-lookup"><span data-stu-id="cf9f3-139">IDENTITY_ATTRIBUTE Structure</span></span>](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-structure.md)  
 [<span data-ttu-id="cf9f3-140">Fusion-Strukturen</span><span class="sxs-lookup"><span data-stu-id="cf9f3-140">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
