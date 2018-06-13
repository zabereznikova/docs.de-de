---
title: Sicherheit von Abhängigkeitseigenschaften
ms.date: 03/30/2017
helpviewer_keywords:
- wrappers [WPF], access
- wrappers [WPF], security
- dependency properties [WPF], security
- security [WPF], wrappers
- validation [WPF], dependency properties
- dependency properties [WPF], access
- security [WPF], dependency properties
ms.assetid: d10150ec-90c5-4571-8d35-84bafa2429a4
ms.openlocfilehash: 825b2a3dc79300f0cc26514398b8de0abee64fd4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33540503"
---
# <a name="dependency-property-security"></a>Sicherheit von Abhängigkeitseigenschaften
Abhängigkeitseigenschaften sollten im Allgemeinen als öffentliche Eigenschaften betrachtet werden. Die Art des [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Eigenschaftensystems verhindert die Möglichkeit von Sicherheitsgarantien in Bezug auf einen Abhängigkeitseigenschaftswert.  
  
  
<a name="AccessSecurity"></a>   
## <a name="access-and-security-of-wrappers-and-dependency-properties"></a>Zugriff und Sicherheit von Wrappern und Abhängigkeitseigenschaften  
 Abhängigkeitseigenschaften werden in der Regel zusammen mit [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]-Wrappereigenschaften implementiert, die das Abrufen oder Festlegen der Eigenschaft aus einer Instanz vereinfachen. Die Wrapper sind nur Hilfsmethoden, die die zugrunde liegende implementieren jedoch <xref:System.Windows.DependencyObject.GetValue%2A> und <xref:System.Windows.DependencyObject.SetValue%2A> statischen Aufrufe, die bei der Interaktion mit Abhängigkeitseigenschaften verwendet werden. Anders formuliert werden die Eigenschaften als [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]-Eigenschaften verfügbar gemacht, die durch eine Abhängigkeitseigenschaft anstatt durch ein privates Feld gesichert werden. Auf Wrapper angewendete Sicherheitsmechanismen gelten nicht parallel zum Verhalten des Eigenschaftensystems und zum Zugriff auf die zugrunde liegende Abhängigkeitseigenschaft. Platzieren eine sicherheitsforderung auf den Wrapper wird nur verhindert, dass die Verwendung der Methode halber aber wird nicht verhindert, dass Aufrufe <xref:System.Windows.DependencyObject.GetValue%2A> oder <xref:System.Windows.DependencyObject.SetValue%2A>. Auch bietet das Versehen der Wrapper mit geschützten oder privaten Zugriffsebenen keine effektive Sicherheit.  
  
 Wenn Sie Ihre eigenen Abhängigkeitseigenschaften schreiben, sollten Sie die Wrapper deklarieren und die <xref:System.Windows.DependencyProperty> Bezeichner Feld als öffentliche Member auf, sodass Aufrufer nicht Informationen zu dieser Eigenschaft die "true" Zugriffsebene (aufgrund der Speicher wird irreführend sein, Abrufen eine Abhängigkeitseigenschaft implementiert).  
  
 Für eine benutzerdefinierte Abhängigkeitseigenschaft können Sie Ihre Eigenschaft als schreibgeschützte Abhängigkeitseigenschaft registrieren, und dies bietet eine effektive Möglichkeit verhindert, dass eine festgelegte Eigenschaft wird von jedem Benutzer, die nicht enthält einen Verweis auf die <xref:System.Windows.DependencyPropertyKey> für diese Eigenschaft. Weitere Informationen finden Sie unter [Schreibgeschützte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/read-only-dependency-properties.md).  
  
> [!NOTE]
>  Deklarieren einer <xref:System.Windows.DependencyProperty> Bezeichner Feld ist nicht unzulässig, und es ist vorstellbar, verringern die unmittelbar verfügbar gemachten Namespace einer benutzerdefinierten Klasse verwendet werden, aber eine solche Eigenschaft sollte weder als "private" im gleichen Sinne wie die [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Sprachdefinitionen definieren diese Zugriffsebene im nächsten Abschnitt beschriebenen Gründen.  
  
<a name="PropertySystemExposure"></a>   
## <a name="property-system-exposure-of-dependency-properties"></a>Offenlegen des Eigenschaftensystems von Abhängigkeitseigenschaften  
 Es ist nicht in der Regel sinnvoll und potenziell irreführend, deklarieren einen <xref:System.Windows.DependencyProperty> wie jede andere als öffentliche Zugriffsebene. Diese Zugriffsebeneneinstellung verhindert lediglich, dass jemand einen Verweis auf die Instanz aus der deklarierenden Klasse erhält. Aber es gibt verschiedene Aspekte des Eigenschaftensystems, die zurückgegeben wird, ein <xref:System.Windows.DependencyProperty> als Mittel zum Identifizieren einer bestimmten Eigenschaft, wie sie auf eine Instanz einer Klasse oder Instanz einer abgeleiteten Klasse vorhanden ist und dieser Bezeichner weiterhin verwendet werden kann, in wird eine <xref:System.Windows.DependencyObject.SetValue%2A> selbst aufrufen Wenn der ursprüngliche statische Bezeichner als nicht öffentlich deklariert ist. Darüber hinaus <xref:System.Windows.DependencyObject.OnPropertyChanged%2A> virtuelle Methoden erhalten Sie Informationen zu einer vorhandenen Abhängigkeitseigenschaft, der Wert geändert. Darüber hinaus die <xref:System.Windows.DependencyObject.GetLocalValueEnumerator%2A> Methodenrückgabe-IDs für jede Eigenschaft von Instanzen mit einem lokal festgelegten Wert.  
  
### <a name="validation-and-security"></a>Validierung und Sicherheit  
 Eine Anforderung zum Anwenden einer <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> und erwartet die Überprüfungsfehler bei Bedarf zu verhindern, dass eine Eigenschaft festgelegt ist kein geeigneter Sicherheitsmechanismus. Setzen Sie den-Registrierungswert invalidierung durch erzwungen <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> kann auch durch böswillige Aufrufer unterdrückt werden, wenn diese Aufrufer innerhalb der Anwendungsdomäne ausgeführt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)
