---
title: IDENTITY_ATTRIBUTE_BLOB-Struktur
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- IDENTITY_ATTRIBUTE_BLOB
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDENTITY_ATTRIBUTE_BLOB
helpviewer_keywords:
- IDENTITY_ATTRIBUTE_BLOB structure [.NET Framework fusion]
ms.assetid: af14ae5f-d226-47dd-ba90-8fc6e6605d4d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 58ee2764d2e2c4c4e21effa3e0c3551a2e145f40
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796507"
---
# <a name="identity_attribute_blob-structure"></a><span data-ttu-id="980b2-102">IDENTITY_ATTRIBUTE_BLOB-Struktur</span><span class="sxs-lookup"><span data-stu-id="980b2-102">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>
<span data-ttu-id="980b2-103">Enthält Informationen zu einem einzelnen Attribut in einer Assembly und besteht aus drei `DWORD`s.</span><span class="sxs-lookup"><span data-stu-id="980b2-103">Contains information about a single attribute in an assembly, and consists of three `DWORD`s.</span></span> <span data-ttu-id="980b2-104">Jeder `DWORD` ist ein Offset in einem Zeichen Puffer, der von `CurrentIntoBuffer` der-Methode der [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) -Schnittstelle erzeugt wird.</span><span class="sxs-lookup"><span data-stu-id="980b2-104">Each `DWORD` is an offset into a character buffer produced by the `CurrentIntoBuffer` method of the [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) interface</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="980b2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="980b2-105">Syntax</span></span>  
  
```cpp  
typedef struct _IDENTITY_ATTRIBUTE_BLOB {  
    DWORD  ofsNamespace;  
    DWORD  ofsName;  
    DWORD  ofsValue;  
}   IDENTITY_ATTRIBUTE_BLOB;  
```  
  
## <a name="members"></a><span data-ttu-id="980b2-106">Member</span><span class="sxs-lookup"><span data-stu-id="980b2-106">Members</span></span>  
  
|<span data-ttu-id="980b2-107">Member</span><span class="sxs-lookup"><span data-stu-id="980b2-107">Member</span></span>|<span data-ttu-id="980b2-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="980b2-108">Description</span></span>|  
|------------|-----------------|  
|`ofsNamespace`|<span data-ttu-id="980b2-109">Der erste Offset im Zeichen Puffer.</span><span class="sxs-lookup"><span data-stu-id="980b2-109">The first offset into the character buffer.</span></span> <span data-ttu-id="980b2-110">Auf diesen Offset folgt nicht der Namespace des Attributs, sondern eine Reihe von NULL Zeichen.</span><span class="sxs-lookup"><span data-stu-id="980b2-110">This offset is not followed by the attribute's namespace, but by a series of null characters.</span></span> <span data-ttu-id="980b2-111">Daher wird Sie nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="980b2-111">Therefore, it is not used.</span></span>|  
|`ofsName`|<span data-ttu-id="980b2-112">Der zweite Offset im Zeichen Puffer.</span><span class="sxs-lookup"><span data-stu-id="980b2-112">The second offset into the character buffer.</span></span> <span data-ttu-id="980b2-113">Dieser Speicherort markiert den Anfang des Attribut namens.</span><span class="sxs-lookup"><span data-stu-id="980b2-113">This location marks the start of the attribute's name.</span></span>|  
|`ofsValue`|<span data-ttu-id="980b2-114">Der dritte Offset im Zeichen Puffer.</span><span class="sxs-lookup"><span data-stu-id="980b2-114">The third offset into the character buffer.</span></span> <span data-ttu-id="980b2-115">Dieser Speicherort markiert den Anfang des Attribut Werts.</span><span class="sxs-lookup"><span data-stu-id="980b2-115">This location marks the start of the attribute's value.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="980b2-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="980b2-116">Sample</span></span>  
 <span data-ttu-id="980b2-117">Im folgenden Beispiel werden mehrere grundlegende Schritte veranschaulicht, die letztendlich zu einer `IDENTITY_ATTRIBUTE_BLOB` aufgefüllten Struktur führen:</span><span class="sxs-lookup"><span data-stu-id="980b2-117">The following example illustrates several basic steps, which eventually result in a populated `IDENTITY_ATTRIBUTE_BLOB` structure:</span></span>  
  
1. <span data-ttu-id="980b2-118">Rufen Sie eine [IReferenceIdentity](ireferenceidentity-interface.md) für die Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="980b2-118">Obtain an [IReferenceIdentity](ireferenceidentity-interface.md) for the assembly.</span></span>  
  
2. <span data-ttu-id="980b2-119">Rufen Sie `IReferenceIdentity::EnumAttributes` die-Methode auf, und rufen Sie eine [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md)ab.</span><span class="sxs-lookup"><span data-stu-id="980b2-119">Call the `IReferenceIdentity::EnumAttributes` method, and obtain an [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md).</span></span>  
  
3. <span data-ttu-id="980b2-120">Erstellen Sie einen Zeichen Puffer, und wandeln Sie ihn `IDENTITY_ATTRIBUTE_BLOB` als-Struktur um.</span><span class="sxs-lookup"><span data-stu-id="980b2-120">Create a character buffer, and cast it as an `IDENTITY_ATTRIBUTE_BLOB` structure.</span></span>  
  
4. <span data-ttu-id="980b2-121">Ruft die `CurrentIntoBuffer` -Methode `IEnumIDENTITY_ATTRIBUTE` der-Schnittstelle auf.</span><span class="sxs-lookup"><span data-stu-id="980b2-121">Call the `CurrentIntoBuffer` method of the `IEnumIDENTITY_ATTRIBUTE` interface.</span></span> <span data-ttu-id="980b2-122">Diese Methode kopiert die Attribute `Namespace`, `Name`und `Value` in den Zeichen Puffer.</span><span class="sxs-lookup"><span data-stu-id="980b2-122">This method copies the attributes `Namespace`, `Name`, and `Value` into the character buffer.</span></span> <span data-ttu-id="980b2-123">Die drei Offsets für diese Zeichen folgen werden in der `IDENTITY_ATTRIBUTE_BLOB` -Struktur verfügbar.</span><span class="sxs-lookup"><span data-stu-id="980b2-123">The three offsets to those strings will become available in the `IDENTITY_ATTRIBUTE_BLOB` structure.</span></span>  
  
```cpp  
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
  
### <a name="to-run-the-sample"></a><span data-ttu-id="980b2-124">So führen Sie das Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="980b2-124">To run the sample</span></span>  
 <span data-ttu-id="980b2-125">C:\\> enumassemblyattribute. exe C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\System.dll</span><span class="sxs-lookup"><span data-stu-id="980b2-125">C:\\> EnumAssemblyAttributes.exe C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\System.dll</span></span>  
  
### <a name="sample-output"></a><span data-ttu-id="980b2-126">Beispielausgabe:</span><span class="sxs-lookup"><span data-stu-id="980b2-126">Sample output</span></span>  
 <span data-ttu-id="980b2-127">Culture = neutral</span><span class="sxs-lookup"><span data-stu-id="980b2-127">Culture = neutral</span></span>  
  
 <span data-ttu-id="980b2-128">Name = System</span><span class="sxs-lookup"><span data-stu-id="980b2-128">name = System</span></span>  
  
 <span data-ttu-id="980b2-129">ProcessorArchitecture = MSIL</span><span class="sxs-lookup"><span data-stu-id="980b2-129">processorArchitecture = MSIL</span></span>  
  
 <span data-ttu-id="980b2-130">PublicKeyToken = b77a5c561934e089</span><span class="sxs-lookup"><span data-stu-id="980b2-130">PublicKeyToken = b77a5c561934e089</span></span>  
  
 <span data-ttu-id="980b2-131">Version = 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="980b2-131">Version = 2.0.0.0</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="980b2-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="980b2-132">Requirements</span></span>  
 <span data-ttu-id="980b2-133">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="980b2-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="980b2-134">**Header:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="980b2-134">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="980b2-135">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="980b2-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="980b2-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="980b2-136">See also</span></span>

- [<span data-ttu-id="980b2-137">IReferenceIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="980b2-137">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)
- [<span data-ttu-id="980b2-138">IEnumIDENTITY_ATTRIBUTE-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="980b2-138">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](ienumidentity-attribute-interface.md)
- [<span data-ttu-id="980b2-139">IDENTITY_ATTRIBUTE-Struktur</span><span class="sxs-lookup"><span data-stu-id="980b2-139">IDENTITY_ATTRIBUTE Structure</span></span>](identity-attribute-structure.md)
- [<span data-ttu-id="980b2-140">Fusion-Strukturen</span><span class="sxs-lookup"><span data-stu-id="980b2-140">Fusion Structures</span></span>](fusion-structures.md)
