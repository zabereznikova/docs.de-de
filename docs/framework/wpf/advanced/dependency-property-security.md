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
ms.openlocfilehash: 85806ee9fb01cd2ca07697230c46a8847fdf8c6a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053547"
---
# <a name="dependency-property-security"></a>Sicherheit von Abhängigkeitseigenschaften
Abhängigkeitseigenschaften sollten im Allgemeinen als öffentliche Eigenschaften betrachtet werden. Die Art des [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Eigenschaftensystems verhindert die Möglichkeit von Sicherheitsgarantien in Bezug auf einen Abhängigkeitseigenschaftswert.  

<a name="AccessSecurity"></a>   
## <a name="access-and-security-of-wrappers-and-dependency-properties"></a>Zugriff und Sicherheit von Wrappern und Abhängigkeitseigenschaften  
 Abhängigkeitseigenschaften werden in der Regel zusammen mit [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]-Wrappereigenschaften implementiert, die das Abrufen oder Festlegen der Eigenschaft aus einer Instanz vereinfachen. Die Wrapper sind einfach nur praktische Methoden, die die zugrunde liegende implementieren jedoch <xref:System.Windows.DependencyObject.GetValue%2A> und <xref:System.Windows.DependencyObject.SetValue%2A> statische Aufrufe, die bei der Interaktion mit Abhängigkeitseigenschaften verwendet werden. Anders formuliert werden die Eigenschaften als [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]-Eigenschaften verfügbar gemacht, die durch eine Abhängigkeitseigenschaft anstatt durch ein privates Feld gesichert werden. Auf Wrapper angewendete Sicherheitsmechanismen gelten nicht parallel zum Verhalten des Eigenschaftensystems und zum Zugriff auf die zugrunde liegende Abhängigkeitseigenschaft. Platzieren eine sicherheitsforderung für den Wrapper wird nur verhindert, dass die Verwendung der Hilfsmethode aber wird nicht verhindert, dass Aufrufe von <xref:System.Windows.DependencyObject.GetValue%2A> oder <xref:System.Windows.DependencyObject.SetValue%2A>. Auch bietet das Versehen der Wrapper mit geschützten oder privaten Zugriffsebenen keine effektive Sicherheit.  
  
 Wenn Sie Ihre eigenen Abhängigkeitseigenschaften schreiben, sollten Sie die Wrapper deklarieren und die <xref:System.Windows.DependencyProperty> -Bezeichnerfeld als öffentliche Member an, sodass Aufrufer keine Informationen über die wahre Zugriffsebene dieser Eigenschaft (aufgrund der Speicher wird irreführenden geltenden erhalten eine Abhängigkeitseigenschaft implementiert).  
  
 Sie können die Eigenschaft als schreibgeschützte Abhängigkeitseigenschaft registrieren, für eine benutzerdefinierte Abhängigkeitseigenschaft, und dies bietet eine effektive Möglichkeit zum Verhindern von jedem Benutzer, die einen Verweis auf nicht aufrechterhält Festlegen der Eigenschaft der <xref:System.Windows.DependencyPropertyKey> für diese Eigenschaft. Weitere Informationen finden Sie unter [Schreibgeschützte Abhängigkeitseigenschaften](read-only-dependency-properties.md).  
  
> [!NOTE]
>  Deklarieren einer <xref:System.Windows.DependencyProperty> privat ist zwar zulässig, und es ist vorstellbar, dass dienen, um den sofort offengelegten Namespace einer benutzerdefinierten Klasse zu reduzieren, aber eine solche Eigenschaft sollte weder als "private", in dem Sinne wie die [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Diese Zugriffsebene im nächsten Abschnitt beschriebenen Gründen definiert.  
  
<a name="PropertySystemExposure"></a>   
## <a name="property-system-exposure-of-dependency-properties"></a>Offenlegen des Eigenschaftensystems von Abhängigkeitseigenschaften  
 Es ist nicht in der Regel sinnvoll, und es ist sogar irreführend sein, um zu deklarieren eine <xref:System.Windows.DependencyProperty> wie jede andere als öffentliche Zugriffsebene. Diese Zugriffsebeneneinstellung verhindert lediglich, dass jemand einen Verweis auf die Instanz aus der deklarierenden Klasse erhält. Es gibt jedoch mehrere Aspekte des Eigenschaftensystems, der zurückgegeben wird ein <xref:System.Windows.DependencyProperty> als Mittel zur Identifizierung einer bestimmten Eigenschaft, wie sie auf eine Instanz einer Klasse oder einer abgeleiteten Klasseninstanz vorhanden ist, und dieser Bezeichner, kann ist ein <xref:System.Windows.DependencyObject.SetValue%2A> selbst aufrufen Wenn der ursprüngliche statische Bezeichner als nicht öffentlich deklariert wird. Darüber hinaus <xref:System.Windows.DependencyObject.OnPropertyChanged%2A> virtuelle Methoden erhalten Sie Informationen zu jeder vorhandenen Abhängigkeitseigenschaft, der Wert geändert. Darüber hinaus die <xref:System.Windows.DependencyObject.GetLocalValueEnumerator%2A> Methodenrückgabe Bezeichner für jede Eigenschaft in Instanzen mit einem lokal festgelegten Wert.  
  
### <a name="validation-and-security"></a>Validierung und Sicherheit  
 Eine Anforderung zum Anwenden einer <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> und erwartet wird der Fehler bei der Überprüfung auf einen Fehler bei Bedarf, um zu verhindern, dass eine Eigenschaft festgelegt wird, ist kein geeigneter Sicherheitsmechanismus. Ungültigkeit von festgelegten Werten durch erzwungen <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> kann auch von böswilligen Aufrufern unterdrückt werden, wenn diese Aufrufer innerhalb der Anwendungsdomäne ausgeführt werden.  
  
## <a name="see-also"></a>Siehe auch

- [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md)
