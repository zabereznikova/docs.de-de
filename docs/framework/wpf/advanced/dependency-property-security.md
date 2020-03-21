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
ms.openlocfilehash: f5640b348ccd68819052f58756489489371862d0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186398"
---
# <a name="dependency-property-security"></a>Sicherheit von Abhängigkeitseigenschaften
Abhängigkeitseigenschaften sollten im Allgemeinen als öffentliche Eigenschaften betrachtet werden. Die Art des [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Eigenschaftensystems verhindert die Möglichkeit von Sicherheitsgarantien in Bezug auf einen Abhängigkeitseigenschaftswert.  

<a name="AccessSecurity"></a>
## <a name="access-and-security-of-wrappers-and-dependency-properties"></a>Zugriff und Sicherheit von Wrappern und Abhängigkeitseigenschaften  
 In der Regel werden Abhängigkeitseigenschaften zusammen mit CLR-Eigenschaften ("wrapper" (Common Language Runtime) implementiert, die das Abrufen oder Festlegen der Eigenschaft von einer Instanz vereinfachen. Aber die Wrapper sind wirklich nur Convenience-Methoden, die die zugrunde liegenden <xref:System.Windows.DependencyObject.GetValue%2A> und <xref:System.Windows.DependencyObject.SetValue%2A> statischen Aufrufe implementieren, die bei der Interaktion mit Abhängigkeitseigenschaften verwendet werden. Wenn man es auf andere Weise bedenkt, werden die Eigenschaften als CLR-Eigenschaften (Common Language Runtime) verfügbar gemacht, die zufällig von einer Abhängigkeitseigenschaft und nicht von einem privaten Feld unterstützt werden. Auf Wrapper angewendete Sicherheitsmechanismen gelten nicht parallel zum Verhalten des Eigenschaftensystems und zum Zugriff auf die zugrunde liegende Abhängigkeitseigenschaft. Wenn Sie eine Sicherheitsanforderung auf den Wrapper setzen, wird nur <xref:System.Windows.DependencyObject.GetValue%2A> die <xref:System.Windows.DependencyObject.SetValue%2A>Verwendung der Convenience-Methode verhindert, aber nicht Aufrufe von oder . Auch bietet das Versehen der Wrapper mit geschützten oder privaten Zugriffsebenen keine effektive Sicherheit.  
  
 Wenn Sie ihre eigenen Abhängigkeitseigenschaften schreiben, sollten Sie <xref:System.Windows.DependencyProperty> die Wrapper und das Bezeichnerfeld als öffentliche Member deklarieren, damit Aufrufer keine irreführenden Informationen über die tatsächliche Zugriffsebene dieser Eigenschaft erhalten (da ihr Speicher als Abhängigkeitseigenschaft implementiert wird).  
  
 Für eine benutzerdefinierte Abhängigkeitseigenschaft können Sie Ihre Eigenschaft als schreibgeschützte Abhängigkeitseigenschaft registrieren, und dies stellt eine effektive <xref:System.Windows.DependencyPropertyKey> Möglichkeit dar, zu verhindern, dass eine Eigenschaft von allen Personen festgelegt wird, die keinen Verweis auf die für diese Eigenschaft enthalten. Weitere Informationen finden Sie unter [Schreibgeschützte Abhängigkeitseigenschaften](read-only-dependency-properties.md).  
  
> [!NOTE]
> Das Deklarieren eines <xref:System.Windows.DependencyProperty> Bezeichnerfelds ist nicht verboten und kann möglicherweise verwendet werden, um den sofort verfügbar gemachten Namespace einer benutzerdefinierten Klasse zu reduzieren, aber eine solche Eigenschaft sollte aus gründenden Gründen nicht als "privat" im gleichen Sinne betrachtet werden, wie die Definitionen der Common Language Runtime (CLR)-Sprachdefinitionen diese Zugriffsebene definieren.  
  
<a name="PropertySystemExposure"></a>
## <a name="property-system-exposure-of-dependency-properties"></a>Offenlegen des Eigenschaftensystems von Abhängigkeitseigenschaften  
 Es ist im Allgemeinen nicht nützlich und potenziell <xref:System.Windows.DependencyProperty> irreführend, eine andere Zugangsstufe als öffentlich zu deklarieren. Diese Zugriffsebeneneinstellung verhindert lediglich, dass jemand einen Verweis auf die Instanz aus der deklarierenden Klasse erhält. Es gibt jedoch mehrere Aspekte des Eigenschaftensystems, die eine <xref:System.Windows.DependencyProperty> als Mittel zum Identifizieren einer bestimmten Eigenschaft zurückgeben, wie sie für eine <xref:System.Windows.DependencyObject.SetValue%2A> Instanz einer Klasse oder einer abgeleiteten Klasseninstanz vorhanden ist, und dieser Bezeichner ist in einem Aufruf immer noch verwendbar, auch wenn der ursprüngliche statische Bezeichner als nicht öffentlich deklariert wird. Außerdem <xref:System.Windows.DependencyObject.OnPropertyChanged%2A> erhalten virtuelle Methoden Informationen über alle vorhandenen Abhängigkeitseigenschaften, die den Wert geändert haben. Darüber hinaus <xref:System.Windows.DependencyObject.GetLocalValueEnumerator%2A> gibt die Methode Bezeichner für jede Eigenschaft für Instanzen mit einem lokal festgelegten Wert zurück.  
  
### <a name="validation-and-security"></a>Validierung und Sicherheit  
 Das Anwenden einer <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> Anforderung auf eine und das Erwarten eines Validierungsfehlers bei einem Anforderungsfehler, bei dem verhindert wird, dass eine Eigenschaft festgelegt wird, ist kein angemessener Sicherheitsmechanismus. Die durch <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> erzwungene Invalidierung von Sollwerten kann auch von böswilligen Aufrufern unterdrückt werden, wenn diese Aufrufer innerhalb der Anwendungsdomäne arbeiten.  
  
## <a name="see-also"></a>Weitere Informationen

- [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md)
