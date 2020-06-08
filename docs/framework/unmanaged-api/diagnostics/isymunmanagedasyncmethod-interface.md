---
title: ISymUnmanagedAsyncMethod-Schnittstelle
ms.date: 03/30/2017
ms.assetid: f2de5224-fd91-45de-9e58-bc600c6d22f1
ms.openlocfilehash: 448ed719331469dce8f15500f14d5c1b0707ecf7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504451"
---
# <a name="isymunmanagedasyncmethod-interface"></a>ISymUnmanagedAsyncMethod-Schnittstelle
Diese Schnittstelle ist die Lese Ergänzung zur [isymunmanagedasyncmethodpropertieswriter-Schnittstelle](isymunmanagedasyncmethodpropertieswriter-interface.md).  
  
## <a name="syntax"></a>Syntax  
  
```idl  
[object,uuid(B20D55B3-532E-4906-87E7-25BD5734ABD2),pointer_default(unique)]interface ISymUnmanagedAsyncMethod : IUnknown  
```  
  
## <a name="methods"></a>Methoden  
 Diese Schnittstelle enthält die folgenden Methoden:  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetAsyncStepInfo-Methode](isymunmanagedasyncmethod-getasyncstepinfo-method.md)|Siehe [defineasyncstepinfo-Methode](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).|  
|[GetAsyncStepInfoCount-Methode](isymunmanagedasyncmethod-getasyncstepinfocount-method.md)|Siehe [defineasyncstepinfo-Methode](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).|  
|[GetCatchHandlerILOffset-Methode](isymunmanagedasyncmethod-getcatchhandleriloffset-method.md)|Siehe [definecatchhandleriloffset-Methode](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).|  
|[GetKickoffMethod-Methode](isymunmanagedasyncmethod-getkickoffmethod-method.md)|Siehe [definekickoffmethod-Methode](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).|  
|[HasCatchHandlerILOffset-Methode](isymunmanagedasyncmethod-hascatchhandleriloffset-method.md)|Siehe [definecatchhandleriloffset-Methode](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).|  
|[IsAsyncMethod-Methode](isymunmanagedasyncmethod-isasyncmethod-method.md)|Überprüft, ob die Methode über asynchrone Informationen verfügt oder nicht.<br /><br /> Wenn diese Methode zurückgibt `FALSE` , ist es ungültig, andere Methoden in dieser Schnittstelle aufzurufen. In diesem Fall werden alle zurückgegeben `E_UNEXPECTED` .|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen:

- [Diagnosesymbolspeicher-Schnittstellen](diagnostics-symbol-store-interfaces.md)
