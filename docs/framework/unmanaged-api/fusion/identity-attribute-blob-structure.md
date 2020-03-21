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
ms.openlocfilehash: 8f838d5c812842e2a637065b25182b6a12609231
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176551"
---
# <a name="identity_attribute_blob-structure"></a><span data-ttu-id="bda3f-102">IDENTITY_ATTRIBUTE_BLOB-Struktur</span><span class="sxs-lookup"><span data-stu-id="bda3f-102">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>
<span data-ttu-id="bda3f-103">Enthält Informationen zu einem einzelnen Attribut in `DWORD`einer Assembly und besteht aus drei s.</span><span class="sxs-lookup"><span data-stu-id="bda3f-103">Contains information about a single attribute in an assembly, and consists of three `DWORD`s.</span></span> <span data-ttu-id="bda3f-104">Jeder `DWORD` ist ein Offset in einen `CurrentIntoBuffer` Zeichenpuffer, der durch die Methode der [IEnumIDENTITY_ATTRIBUTE-Schnittstelle](ienumidentity-attribute-interface.md) erzeugt wird.</span><span class="sxs-lookup"><span data-stu-id="bda3f-104">Each `DWORD` is an offset into a character buffer produced by the `CurrentIntoBuffer` method of the [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) interface</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bda3f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="bda3f-105">Syntax</span></span>  
  
```cpp  
typedef struct _IDENTITY_ATTRIBUTE_BLOB {  
    DWORD  ofsNamespace;  
    DWORD  ofsName;  
    DWORD  ofsValue;  
}   IDENTITY_ATTRIBUTE_BLOB;  
```  
  
## <a name="members"></a><span data-ttu-id="bda3f-106">Members</span><span class="sxs-lookup"><span data-stu-id="bda3f-106">Members</span></span>  
  
|<span data-ttu-id="bda3f-107">Member</span><span class="sxs-lookup"><span data-stu-id="bda3f-107">Member</span></span>|<span data-ttu-id="bda3f-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bda3f-108">Description</span></span>|  
|------------|-----------------|  
|`ofsNamespace`|<span data-ttu-id="bda3f-109">Der erste Offset in den Zeichenpuffer.</span><span class="sxs-lookup"><span data-stu-id="bda3f-109">The first offset into the character buffer.</span></span> <span data-ttu-id="bda3f-110">Auf diesen Offset folgt nicht der Namespace des Attributs, sondern eine Reihe von Nullzeichen.</span><span class="sxs-lookup"><span data-stu-id="bda3f-110">This offset is not followed by the attribute's namespace, but by a series of null characters.</span></span> <span data-ttu-id="bda3f-111">Daher wird es nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="bda3f-111">Therefore, it is not used.</span></span>|  
|`ofsName`|<span data-ttu-id="bda3f-112">Der zweite Offset in den Zeichenpuffer.</span><span class="sxs-lookup"><span data-stu-id="bda3f-112">The second offset into the character buffer.</span></span> <span data-ttu-id="bda3f-113">Diese Position markiert den Anfang des Attributnamens.</span><span class="sxs-lookup"><span data-stu-id="bda3f-113">This location marks the start of the attribute's name.</span></span>|  
|`ofsValue`|<span data-ttu-id="bda3f-114">Der dritte Offset in den Zeichenpuffer.</span><span class="sxs-lookup"><span data-stu-id="bda3f-114">The third offset into the character buffer.</span></span> <span data-ttu-id="bda3f-115">Diese Position markiert den Beginn des Attributwerts.</span><span class="sxs-lookup"><span data-stu-id="bda3f-115">This location marks the start of the attribute's value.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="bda3f-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bda3f-116">Sample</span></span>  
 <span data-ttu-id="bda3f-117">Das folgende Beispiel veranschaulicht mehrere grundlegende Schritte, `IDENTITY_ATTRIBUTE_BLOB` die schließlich zu einer aufgefüllten Struktur führen:</span><span class="sxs-lookup"><span data-stu-id="bda3f-117">The following example illustrates several basic steps, which eventually result in a populated `IDENTITY_ATTRIBUTE_BLOB` structure:</span></span>  
  
1. <span data-ttu-id="bda3f-118">Abrufen einer [IReferenceIdentity](ireferenceidentity-interface.md) für die Assembly.</span><span class="sxs-lookup"><span data-stu-id="bda3f-118">Obtain an [IReferenceIdentity](ireferenceidentity-interface.md) for the assembly.</span></span>  
  
2. <span data-ttu-id="bda3f-119">Rufen `IReferenceIdentity::EnumAttributes` Sie die Methode auf, und rufen Sie eine [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md)ab.</span><span class="sxs-lookup"><span data-stu-id="bda3f-119">Call the `IReferenceIdentity::EnumAttributes` method, and obtain an [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md).</span></span>  
  
3. <span data-ttu-id="bda3f-120">Erstellen Sie einen Zeichenpuffer, `IDENTITY_ATTRIBUTE_BLOB` und geben Sie ihn als Struktur um.</span><span class="sxs-lookup"><span data-stu-id="bda3f-120">Create a character buffer, and cast it as an `IDENTITY_ATTRIBUTE_BLOB` structure.</span></span>  
  
4. <span data-ttu-id="bda3f-121">Rufen `CurrentIntoBuffer` Sie die `IEnumIDENTITY_ATTRIBUTE` Methode der Schnittstelle auf.</span><span class="sxs-lookup"><span data-stu-id="bda3f-121">Call the `CurrentIntoBuffer` method of the `IEnumIDENTITY_ATTRIBUTE` interface.</span></span> <span data-ttu-id="bda3f-122">Diese Methode kopiert `Namespace`die `Name`Attribute `Value` , und in den Zeichenpuffer.</span><span class="sxs-lookup"><span data-stu-id="bda3f-122">This method copies the attributes `Namespace`, `Name`, and `Value` into the character buffer.</span></span> <span data-ttu-id="bda3f-123">Die drei Offsets zu diesen Zeichenfolgen werden in der `IDENTITY_ATTRIBUTE_BLOB` Struktur verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bda3f-123">The three offsets to those strings will become available in the `IDENTITY_ATTRIBUTE_BLOB` structure.</span></span>  
  
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
  
### <a name="to-run-the-sample"></a><span data-ttu-id="bda3f-124">Ausführen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="bda3f-124">To run the sample</span></span>  
 <span data-ttu-id="bda3f-125">C:\\> EnumAssemblyAttributes.exe C:-WINDOWS-Microsoft.NET-Framework-V2.0.50727-System.dll</span><span class="sxs-lookup"><span data-stu-id="bda3f-125">C:\\> EnumAssemblyAttributes.exe C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\System.dll</span></span>  
  
### <a name="sample-output"></a><span data-ttu-id="bda3f-126">Beispielausgabe</span><span class="sxs-lookup"><span data-stu-id="bda3f-126">Sample output</span></span>  
 <span data-ttu-id="bda3f-127">Kultur = neutral</span><span class="sxs-lookup"><span data-stu-id="bda3f-127">Culture = neutral</span></span>  
  
 <span data-ttu-id="bda3f-128">Name = System</span><span class="sxs-lookup"><span data-stu-id="bda3f-128">name = System</span></span>  
  
 <span data-ttu-id="bda3f-129">prozessorArchitektur = MSIL</span><span class="sxs-lookup"><span data-stu-id="bda3f-129">processorArchitecture = MSIL</span></span>  
  
 <span data-ttu-id="bda3f-130">PublicKeyToken = b77a5c561934e089</span><span class="sxs-lookup"><span data-stu-id="bda3f-130">PublicKeyToken = b77a5c561934e089</span></span>  
  
 <span data-ttu-id="bda3f-131">Version = 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="bda3f-131">Version = 2.0.0.0</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bda3f-132">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bda3f-132">Requirements</span></span>  
 <span data-ttu-id="bda3f-133">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bda3f-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bda3f-134">**Kopfzeile:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="bda3f-134">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="bda3f-135">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bda3f-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bda3f-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bda3f-136">See also</span></span>

- [<span data-ttu-id="bda3f-137">IReferenceIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bda3f-137">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)
- [<span data-ttu-id="bda3f-138">IEnumIDENTITY_ATTRIBUTE-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bda3f-138">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](ienumidentity-attribute-interface.md)
- [<span data-ttu-id="bda3f-139">IDENTITY_ATTRIBUTE-Struktur</span><span class="sxs-lookup"><span data-stu-id="bda3f-139">IDENTITY_ATTRIBUTE Structure</span></span>](identity-attribute-structure.md)
- [<span data-ttu-id="bda3f-140">Fusionsstrukturen</span><span class="sxs-lookup"><span data-stu-id="bda3f-140">Fusion Structures</span></span>](fusion-structures.md)
