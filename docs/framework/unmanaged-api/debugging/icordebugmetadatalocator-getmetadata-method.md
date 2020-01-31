---
title: ICorDebugMetaDataLocator::GetMetaData-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugMetaDataLocator.GetMetaData
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMetaDataLocator::GetMetaData
helpviewer_keywords:
- ICorDebugMetaDataLocator::GetMetaData method [.NET Framework debugging]
- GetMetaData method, ICorDebugMetaDataLocator interface [.NET Framework debugging]
ms.assetid: f9b0ff22-54db-45eb-9cc3-508000a3141d
topic_type:
- apiref
ms.openlocfilehash: 43f3c1dd866b98bff51b375a11e28727e41d3ead
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793050"
---
# <a name="icordebugmetadatalocatorgetmetadata-method"></a><span data-ttu-id="11398-102">ICorDebugMetaDataLocator::GetMetaData-Methode</span><span class="sxs-lookup"><span data-stu-id="11398-102">ICorDebugMetaDataLocator::GetMetaData Method</span></span>
<span data-ttu-id="11398-103">Fordert den Debugger auf, den vollständigen Pfad eines Moduls zurückzugeben, dessen Metadaten benötigt werden, um einen vom Debugger angeforderten Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="11398-103">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11398-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="11398-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaData(  
      [in] LPCWSTR wszImagePath,  
      [in] DWORD   dwImageTimeStamp,  
      [in] DWORD   dwImageSize,  
      [in] ULONG32 cchPathBuffer,  
      [out] ULONG32 * pcchPathBuffer,  
      [out, size_is(cchPathBuffer), length_is(*pcchPathBuffer)]  
               WCHAR wszPathBuffer[]  
      );  
```  
  
## <a name="parameters"></a><span data-ttu-id="11398-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="11398-105">Parameters</span></span>  
 `wszImagePath`  
 <span data-ttu-id="11398-106">[in] Eine mit NULL endende Zeichenfolge, die den vollständigen Pfad zu der Datei darstellt.</span><span class="sxs-lookup"><span data-stu-id="11398-106">[in] A null-terminated string that represents the full path to the file.</span></span> <span data-ttu-id="11398-107">Wenn der vollständige Pfad nicht verfügbar ist, der Name und die Erweiterung der Datei (*Dateiname*. *Erweiterung*).</span><span class="sxs-lookup"><span data-stu-id="11398-107">If the full path is not available, the name and extension of the file (*filename*.*extension*).</span></span>  
  
 `dwImageTimeStamp`  
 <span data-ttu-id="11398-108">[in] Der Zeitstempel aus den PE-Dateiheadern des Bilds.</span><span class="sxs-lookup"><span data-stu-id="11398-108">[in] The time stamp from the image's PE file headers.</span></span> <span data-ttu-id="11398-109">Dieser Parameter kann potenziell für einen Symbol Server ([SymSrv](/windows/desktop/debug/using-symsrv))-Lookup verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="11398-109">This parameter can potentially be used for a symbol server ([SymSrv](/windows/desktop/debug/using-symsrv)) lookup.</span></span>  
  
 `dwImageSize`  
 <span data-ttu-id="11398-110">[in] Die Bildgröße aus PE-Dateiheadern.</span><span class="sxs-lookup"><span data-stu-id="11398-110">[in] The image size from PE file headers.</span></span> <span data-ttu-id="11398-111">Dieser Parameter kann potenziell für eine SymSrv-Suche verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="11398-111">This parameter can potentially be used for a SymSrv lookup.</span></span>  
  
 `cchPathBuffer`  
 <span data-ttu-id="11398-112">[in] Die Anzahl der Zeichen in `wszPathBuffer`.</span><span class="sxs-lookup"><span data-stu-id="11398-112">[in] The character count in `wszPathBuffer`.</span></span>  
  
 `pcchPathBuffer`  
 <span data-ttu-id="11398-113">[out] Die Anzahl der `WCHAR` in geschriebenen `wszPathBuffer`.</span><span class="sxs-lookup"><span data-stu-id="11398-113">[out] The count of `WCHAR`s written to `wszPathBuffer`.</span></span>  
  
 <span data-ttu-id="11398-114">Wenn die Methode E_NOT_SUFFICIENT_BUFFER zurückgibt, ist die Anzahl der `WCHAR`s enthalten, die zum Speichern des Pfads erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="11398-114">If the method returns E_NOT_SUFFICIENT_BUFFER, contains the count of `WCHAR`s needed to store the path.</span></span>  
  
 `wszPathBuffer`  
 <span data-ttu-id="11398-115">[out] Ein Zeiger auf einen Puffer, in den der Debugger den vollständigen Pfad der Datei kopiert, die die angeforderten Metadaten enthält.</span><span class="sxs-lookup"><span data-stu-id="11398-115">[out] Pointer to a buffer into which the debugger will copy the full path of the file that contains the requested metadata.</span></span>  
  
 <span data-ttu-id="11398-116">Das `ofReadOnly`-Flag aus der [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) -Enumeration wird verwendet, um schreibgeschützten Zugriff auf die Metadaten in dieser Datei anzufordern.</span><span class="sxs-lookup"><span data-stu-id="11398-116">The `ofReadOnly` flag from the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration is used to request read-only access to the metadata in this file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11398-117">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="11398-117">Return Value</span></span>  
 <span data-ttu-id="11398-118">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="11398-118">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span> <span data-ttu-id="11398-119">Alle anderen Fehler-HRESULTs geben an, dass die Datei nicht abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="11398-119">All other failure HRESULTs indicate that the file is not retrievable.</span></span>  
  
|<span data-ttu-id="11398-120">HRESULT</span><span class="sxs-lookup"><span data-stu-id="11398-120">HRESULT</span></span>|<span data-ttu-id="11398-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11398-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="11398-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="11398-122">S_OK</span></span>|<span data-ttu-id="11398-123">Die Methode wurde abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="11398-123">The method completed successfully.</span></span> <span data-ttu-id="11398-124">`wszPathBuffer` enthält den vollständigen Pfad zu der Datei und endet auf NULL.</span><span class="sxs-lookup"><span data-stu-id="11398-124">`wszPathBuffer` contains the full path to the file and is null-terminated.</span></span>|  
|<span data-ttu-id="11398-125">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="11398-125">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="11398-126">Die aktuelle Größe von `wszPathBuffer` reicht nicht aus, um den vollständigen Pfad aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="11398-126">The current size of `wszPathBuffer` is not sufficient to hold the full path.</span></span> <span data-ttu-id="11398-127">In diesem Fall enthält `pcchPathBuffer` die benötigte Anzahl von `WCHAR`s, einschließlich des abschließenden NULL-Zeichens, und `GetMetaData` wird ein zweites Mal mit der angeforderten Puffergröße aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="11398-127">In this case, `pcchPathBuffer` contains the needed count of `WCHAR`s, including the terminating null character, and `GetMetaData` is called a second time with the requested buffer size.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11398-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="11398-128">Remarks</span></span>  
 <span data-ttu-id="11398-129">Wenn `wszImagePath` einen vollständigen Pfad für ein Modul aus einem Speicherabbild enthält, gibt es den Pfad von dem Computer an, auf dem das Speicherabbild erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="11398-129">If `wszImagePath` contains a full path for a module from a dump, it specifies the path from the computer where the dump was collected.</span></span> <span data-ttu-id="11398-130">Die Datei ist an diesem Speicherort möglicherweise nicht vorhanden, oder es wird eine falsche Datei mit gleichem Namen in diesem Pfad gespeichert.</span><span class="sxs-lookup"><span data-stu-id="11398-130">The file may not exist at this location, or an incorrect file with the same name may be stored on the path.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11398-131">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="11398-131">Requirements</span></span>  
 <span data-ttu-id="11398-132">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11398-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11398-133">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="11398-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11398-134">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11398-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11398-135">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11398-135">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11398-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11398-136">See also</span></span>

- [<span data-ttu-id="11398-137">ICorDebugThread4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="11398-137">ICorDebugThread4 Interface</span></span>](icordebugthread4-interface.md)
- [<span data-ttu-id="11398-138">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="11398-138">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="11398-139">Debuggen</span><span class="sxs-lookup"><span data-stu-id="11398-139">Debugging</span></span>](index.md)
