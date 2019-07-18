---
title: GetRawInputDevices
ms.date: 03/30/2017
helpviewer_keywords:
- raw input [WPF]
ms.assetid: c4d37ecd-065a-4d1c-9e6c-26804ae968ca
ms.openlocfilehash: 3531ff9f42289a3ad3b029f090f2dd4987e5886c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947913"
---
# <a name="getrawinputdevices"></a>GetRawInputDevices
Ermöglicht es der Datei "PresentationHost.exe", Geräte für die Eingabe von Rohdaten (Eingabegeräte, Human Interface Devices) zu erkennen, die für die Hostanwendung interessant sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetRawInputDevices( [out] IEnumRAWINPUTDEVICE **ppEnum );  
```  
  
## <a name="parameters"></a>Parameter  
 `ppEnum`  
  
 [out] Ein Zeiger auf ein [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) zum Aufzählen der Eingabegeräte für Rohdaten.  
  
## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 HRESULT:  
  
 S_OK - [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) wird nur von PresentationHost.exe verwendet werden, wenn S_OK zurückgegeben wird.  
  
 E_NOTIMPL  
  
## <a name="remarks"></a>Hinweise  
 Eingabegeräte für Rohdaten sind Eingabegeräte wie Tastaturen, Mäuse und weniger verbreitete Geräte wie Fernbedienungen.  
  
 Nachdem die Liste der Eingabegeräte für Rohdaten abgerufen wurde, registriert "PresentationHost.exe" diese Geräte, um WM_INPUT-Benachrichtigungen zu erhalten.  
  
## <a name="see-also"></a>Siehe auch

- [GetRawInputDeviceList](/windows/desktop/api/winuser/nf-winuser-getrawinputdevicelist)
- [FilterInputMessage](filterinputmessage.md)
