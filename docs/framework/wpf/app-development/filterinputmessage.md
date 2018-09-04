---
title: FilterInputMessage
ms.date: 03/30/2017
helpviewer_keywords:
- raw input [WPF]
- FilterInputMessage method [WPF]
ms.assetid: 4d74c6cf-7d1d-49ff-96c1-231340ce54f5
ms.openlocfilehash: 1a22071696ca012968e042e15cd8a9f4b876fd9f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43532078"
---
# <a name="filterinputmessage"></a>FilterInputMessage
Wird immer dann von "PresentationHost.exe" aufgerufen, wenn eine Meldung empfangen wurde, es sei denn, E_NOTIMPL wurde zurückgegeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT FilterInputMessage( [in] MSG* pMsg ) ;  
```  
  
#### <a name="parameters"></a>Parameter  
 `pMsg`  
  
 [in] Die WM_INPUT-Meldung, die an das Fenster gesendet wurde, das die unformatierte Eingabe erhält.  
  
## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 HRESULT:  
  
 S_OK – Der Filter hat die Meldung nicht verarbeitet, und weitere Verarbeitungsschritte können folgen.  
  
 S_FALSE – Der Filter hat diese Meldung verarbeitet, und es sollten keine weiteren Verarbeitungsschritte folgen.  
  
 E_NOTIMPL – bei diesem Wert zurückgegeben wird, [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md) nicht erneut aufgerufen. Dieser Wert wird möglicherweise von einer Hostanwendung zurückgegeben, die nur daran interessiert ist, benutzerdefinierte Status- und Fehlerbenutzeroberflächen für "PresentationHost.exe" bereitzustellen, und nicht dafür vorgesehen ist, unformatierte Eingabemeldungen von "PresentationHost.exe" weiterzuleiten.  
  
## <a name="remarks"></a>Hinweise  
 "PresentationHost.exe" ist das Ziel von verschiedenen Geräten für unformatierte Eingabe, einschließlich Tastatur, Mäusen und Fernsteuerungen. Manchmal hängt das Verhalten in der Hostanwendung von einer Eingabe ab, die andernfalls von "PresentationHost.exe" verarbeitet werden würde. Beispielsweise kann für eine Hostanwendung das Empfangen bestimmter Eingabemeldungen erforderlich sein, um bestimmen zu können, ob bestimmte Elemente der Benutzeroberfläche angezeigt werden sollen oder nicht.  
  
 Damit die hostanwendung diese Verhaltensweisen zu den erforderlichen eingabemeldungen empfangen kann, leitet PresentationHost.exe an die gehostete Anwendung entsprechende unformatierte eingabemeldungen durch Aufrufen von [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md).  
  
 Die gehostete Anwendung empfängt unformatierte eingabemeldungen durch die Registrierung mit dem Satz von Geräten für unformatierte Eingabe (Human Interface Devices) vom [GetRawInputDevices](../../../../docs/framework/wpf/app-development/getrawinputdevices.md).  
  
## <a name="see-also"></a>Siehe auch  
 [WM_INPUT-Benachrichtigung](https://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputmessages/wm_input.asp)
