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
ms.openlocfilehash: d9dd9306980b80f7845c10e8c0ccb59f29821245
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940838"
---
# <a name="dependency-property-security"></a>Sicherheit von Abhängigkeitseigenschaften
Abhängigkeitseigenschaften sollten im Allgemeinen als öffentliche Eigenschaften betrachtet werden. Die Art des [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Eigenschaftensystems verhindert die Möglichkeit von Sicherheitsgarantien in Bezug auf einen Abhängigkeitseigenschaftswert.  

<a name="AccessSecurity"></a>   
## <a name="access-and-security-of-wrappers-and-dependency-properties"></a>Zugriff und Sicherheit von Wrappern und Abhängigkeitseigenschaften  
 Abhängigkeits Eigenschaften werden in der Regel zusammen mit den Eigenschaften von "Wrapper" Common Language Runtime (CLR) implementiert, die das zurück-oder Festlegen der-Eigenschaft aus einer-Instanz vereinfachen. Die Wrapper sind jedoch nur praktische Methoden, mit denen die zugrunde liegenden <xref:System.Windows.DependencyObject.GetValue%2A> und <xref:System.Windows.DependencyObject.SetValue%2A> statischen Aufrufe implementiert werden, die bei der Interaktion mit Abhängigkeits Eigenschaften verwendet werden. Anders gesagt, werden die Eigenschaften als Common Language Runtime (CLR)-Eigenschaften verfügbar gemacht, die durch eine Abhängigkeits Eigenschaft und nicht durch ein privates Feld unterstützt werden. Auf Wrapper angewendete Sicherheitsmechanismen gelten nicht parallel zum Verhalten des Eigenschaftensystems und zum Zugriff auf die zugrunde liegende Abhängigkeitseigenschaft. Wenn Sie <xref:System.Windows.DependencyObject.GetValue%2A> einen Sicherheitsbedarf für den Wrapper festlegen, wird nur die Verwendung der Hilfsmethode verhindert, es werden jedoch keine <xref:System.Windows.DependencyObject.SetValue%2A>Aufrufe von oder verhindert. Auch bietet das Versehen der Wrapper mit geschützten oder privaten Zugriffsebenen keine effektive Sicherheit.  
  
 Wenn Sie eigene Abhängigkeits Eigenschaften schreiben, sollten Sie die Wrapper und das <xref:System.Windows.DependencyProperty> Bezeichnerfeld als öffentliche Member deklarieren, damit Aufrufer keine irreführenden Informationen über die tatsächliche Zugriffsebene dieser Eigenschaft erhalten (weil der Speicher wird als Abhängigkeits Eigenschaft implementiert.)  
  
 Bei einer benutzerdefinierten Abhängigkeits Eigenschaft können Sie die-Eigenschaft als schreibgeschützte Abhängigkeits Eigenschaft registrieren. Dies stellt eine effektive Methode dar, um zu verhindern, dass eine Eigenschaft von allen Personen festgelegt wird, die <xref:System.Windows.DependencyPropertyKey> keinen Verweis auf die für diese Eigenschaft enthalten. Weitere Informationen finden Sie unter [Schreibgeschützte Abhängigkeitseigenschaften](read-only-dependency-properties.md).  
  
> [!NOTE]
> Das Deklarieren eines <xref:System.Windows.DependencyProperty> privaten Bezeichnerfelds ist nicht unzulässig und kann verwendet werden, um den sofort verfügbar gemachten Namespace einer benutzerdefinierten Klasse zu verringern. eine solche Eigenschaft sollte jedoch nicht als "Privat" betrachtet werden, wie die Common Language. Lauf Zeitdefinitionen (Common Language Runtime, CLR) definieren diese Zugriffsebene aus den im nächsten Abschnitt beschriebenen Gründen.  
  
<a name="PropertySystemExposure"></a>   
## <a name="property-system-exposure-of-dependency-properties"></a>Offenlegen des Eigenschaftensystems von Abhängigkeitseigenschaften  
 Es ist in der Regel nicht nützlich, und es ist möglicherweise irreführend <xref:System.Windows.DependencyProperty> , einen als jede andere Zugriffsebene als Public zu deklarieren. Diese Zugriffsebeneneinstellung verhindert lediglich, dass jemand einen Verweis auf die Instanz aus der deklarierenden Klasse erhält. Es gibt jedoch mehrere Aspekte des-Eigenschaften Systems, die einen <xref:System.Windows.DependencyProperty> zurückgeben, um eine bestimmte Eigenschaft zu identifizieren, wie Sie in einer Instanz einer Klasse oder einer abgeleiteten Klasseninstanz vorhanden ist, und dieser Bezeichner kann weiterhin in einem <xref:System.Windows.DependencyObject.SetValue%2A> -Rückruf verwendet werden. , wenn der ursprüngliche statische Bezeichner als nicht öffentlich deklariert ist. Außerdem erhalten <xref:System.Windows.DependencyObject.OnPropertyChanged%2A> virtuelle Methoden Informationen zu jeder vorhandenen Abhängigkeits Eigenschaft, die den Wert geändert hat. Außerdem gibt die <xref:System.Windows.DependencyObject.GetLocalValueEnumerator%2A> -Methode Bezeichner für jede Eigenschaft von-Instanzen mit einem lokal festgelegten Wert zurück.  
  
### <a name="validation-and-security"></a>Validierung und Sicherheit  
 Das Anwenden einer Anforderung auf <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> einen und das erwarten des Überprüfungs Fehlers bei einem Anforderungs Fehler, um zu verhindern, dass eine Eigenschaft festgelegt wird, ist kein geeigneter Sicherheitsmechanismus. Die durch <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> erzwungene Festlegung von Wert Invalidierung kann auch von bösartigen Aufrufern unterdrückt werden, wenn diese Aufrufer innerhalb der Anwendungsdomäne arbeiten.  
  
## <a name="see-also"></a>Siehe auch

- [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md)
