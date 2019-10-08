---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: e9ef32912c2afb3c99e46e1e14bb3daa5a2e99af
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005707"
---
# <a name="getcustomui"></a>GetCustomUI
Wird von "PresentationHost. exe" aufgerufen, um beim implementieren benutzerdefinierte Status-und Fehlermeldungen vom Host zu erhalten.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
## <a name="parameters"></a>Parameter  
 `pwzProgressAssemblyName`  
  
 vorgenommen Ein Zeiger auf die Assembly, die die vom Host bereitgestellte Status-Benutzeroberfläche enthält.  
  
 `pwzProgressClassName`  
  
 vorgenommen Der Name der Klasse, die die vom Host bereitgestellte Status-Benutzeroberfläche ist, vorzugsweise eine XAML-Datei mit <xref:System.Windows.Controls.Page> ist das Element der obersten Ebene. Diese Klasse befindet sich in der Assembly, die durch `pwzProgressAssemblyName` angegeben wird.  
  
 `pwzErrorAssemblyName`  
  
 vorgenommen Ein Zeiger auf die Assembly, die die vom Host bereitgestellte Fehler Benutzeroberfläche enthält.  
  
 `pwzErrorClassName`  
  
 vorgenommen Der Name der Klasse, die die vom Host bereitgestellte Fehler Benutzeroberfläche ist, vorzugsweise eine XAML-Datei mit <xref:System.Windows.Controls.Page> ist das Element der obersten Ebene. Diese Klasse befindet sich in der Assembly, die durch `pwzErrorAssemblyName` angegeben wird.  
  
## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 HRESULT: Ignoriert.  
  
## <a name="remarks"></a>Hinweise  
 Eine Host Anwendung kann über ein bestimmtes Design verfügen, das von den Standardbenutzer Oberflächen von PresentationHost. exe möglicherweise nicht konform ist. Wenn dies der Fall ist, kann die Host Anwendung [GetCustomUI](getcustomui.md) implementieren, um den Fortschritt und Fehler Benutzerschnittstellen an PresentationHost. exe zurückzugeben. "PresentationHost. exe" ruft immer " [GetCustomUI](getcustomui.md) " auf, bevor die Standardbenutzer Oberflächen verwendet werden.  
  
 Diese Funktion wird während der PresentationHost-Initialisierung einmal aufgerufen.  
  
## <a name="see-also"></a>Siehe auch

- [IWpfHostSupport](iwpfhostsupport.md)
