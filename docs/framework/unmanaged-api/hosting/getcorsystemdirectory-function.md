---
title: GetCORSystemDirectory-Funktion
ms.date: 03/30/2017
api_name:
- GetCORSystemDirectory
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORSystemDirectory
helpviewer_keywords:
- GetCORSystemDirectory function [.NET Framework hosting]
ms.assetid: 3dcd16a7-dafc-4ca8-b5cd-20ffb37db91d
topic_type:
- apiref
ms.openlocfilehash: 21b01156afceb24ab5c132894fae6922d7b97e59
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733294"
---
# <a name="getcorsystemdirectory-function"></a>GetCORSystemDirectory-Funktion

Gibt das Installationsverzeichnis des Common Language Runtime (CLR) zurück, das in den Prozess geladen wird. Das Installationsverzeichnis ist voll qualifiziert, z. b. "c:\WINDOWS\Microsoft.NET\Framework\v1.0.3705".  
  
 Diese Funktion ist als veraltet markiert. Sie wird durch die [iclrruntimumfo:: getruntimedirectory](iclrruntimeinfo-getruntimedirectory-method.md) -Methode abgelöst, die in der .NET Framework 4 bereitgestellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetCORSystemDirectory (
    [out] LPWSTR  pbuffer,
    [in]  DWORD   cchBuffer,
    [out] DWORD*  dwlength  
);
```  
  
## <a name="parameters"></a>Parameter  

 `pbuffer`  
 vorgenommen Ein Puffer, in dem die Laufzeit eine Zeichenfolge zurückgibt, die den voll qualifizierten Namen des Installationsverzeichnisses für die Laufzeit enthält, die in den Prozess geladen wird. Wenn die Laufzeit noch nicht in den Prozess geladen wurde, gibt die Funktion die entsprechenden Verzeichnisinformationen für die aktuelle Version der Laufzeit zurück, die auf dem Computer installiert ist.  
  
 `cchBuffer`  
 in Die Größe von in Bytes `pbuffer` .  
  
 `dwLength`  
 vorgenommen Die Anzahl der Zeichen, die in zurückgegeben werden `pbuffer` .  
  
## <a name="remarks"></a>Hinweise  
  
> [!CAUTION]
> Verwenden Sie diese Funktion nicht in Prozessen, in denen Version 4 der CLR ausgeführt wird. Wenn eine frühere Version der CLR auf dem Computer installiert ist, gibt diese Funktion das Installationsverzeichnis für diese Version zurück.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md)
