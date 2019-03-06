---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: af51a0d76ac080017f58ac8fc3acca86c23fb480
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474864"
---
# <a name="getcustomui"></a>GetCustomUI
Vom PresentationHost.exe abzurufenden benutzerdefinierte Status- und Fehlermeldungen vom Host aufgerufen, wenn es sich bei implementiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
## <a name="parameters"></a>Parameter  
 `pwzProgressAssemblyName`  
  
 [out] Ein Zeiger auf die Assembly mit dem Host bereitgestellte tasksequenzstatus-Benutzeroberfläche.  
  
 `pwzProgressClassName`  
  
 [out] Der Name der Klasse an, die Benutzeroberfläche für den Host bereitgestellter Status, vorzugsweise einen [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] -Datei mit <xref:System.Windows.Controls.Page> Element der obersten Ebene. Diese Klasse befindet sich in der Assembly, die angegebenen `pwzProgressAssemblyName`.  
  
 `pwzErrorAssemblyName`  
  
 [out] Ein Zeiger auf die Assembly, die die Benutzeroberfläche für den Host angegebene Fehler enthält.  
  
 `pwzErrorClassName`  
  
 [out] Der Name der Klasse, die der Host angegebene Benutzer ist Schnittstelle, von denen vorzugsweise eine XAML-Datei mit <xref:System.Windows.Controls.Page> Element der obersten Ebene. Diese Klasse befindet sich in der Assembly, die angegebenen `pwzErrorAssemblyName`.  
  
## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 HRESULT: Ignoriert.  
  
## <a name="remarks"></a>Hinweise  
 Eine hostanwendung möglicherweise ein bestimmtes Design, dem die PresentationHost.exe standardmäßigen Benutzeroberflächen von nicht entspricht. Wenn dies der Fall ist, kann die hostanwendung implementieren [GetCustomUI](getcustomui.md) Status- und Benutzeroberflächen für PresentationHost.exe zurückgegeben. Rufen Sie PresentationHost.exe wird immer [GetCustomUI](getcustomui.md) vor der Verwendung der standardmäßigen Benutzeroberflächen.  
  
 Diese Funktion wird einmal während der Initialisierung von PresentationHost aufgerufen.  
  
## <a name="see-also"></a>Siehe auch
- [IWpfHostSupport](iwpfhostsupport.md)
