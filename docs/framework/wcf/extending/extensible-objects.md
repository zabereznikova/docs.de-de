---
title: Erweiterbare Objekte
ms.date: 03/30/2017
helpviewer_keywords:
- extensible objects [WCF]
ms.assetid: bc88cefc-31fb-428e-9447-6d20a7d452af
ms.openlocfilehash: 95bd354e3aed8e0968debcac160383eb9c26cd0a
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33805196"
---
# <a name="extensible-objects"></a>Erweiterbare Objekte
Das erweiterbare Objektmuster wird verwendet, um entweder vorhandene Laufzeitklassen um neue Funktionen zu erweitern oder um einem Objekt neue Zustandsfunktionen hinzuzufügen. Erweiterungen, die einem der erweiterbaren Objekte zugeordnet sind, ermöglichen es Verhalten in verschiedenen Phasen der Verarbeitung, auf gemeinsam verwendete Zustände und Funktionen zuzugreifen, die an ein zugängliches und allgemeines erweiterbares Objekt angefügt sind.  
  
## <a name="the-iextensibleobjectt-pattern"></a>Die IExtensibleObject\<T > Muster  
 Es gibt drei Schnittstellen im erweiterbaren Objektmuster: <xref:System.ServiceModel.IExtensibleObject%601>, <xref:System.ServiceModel.IExtension%601> und <xref:System.ServiceModel.IExtensionCollection%601>.  
  
 Die <xref:System.ServiceModel.IExtensibleObject%601>-Schnittstelle wird von Typen implementiert, die es <xref:System.ServiceModel.IExtension%601>-Objekten ermöglichen, ihre Funktionalität anzupassen.  
  
 Erweiterbare Objekte ermöglichen die dynamische Aggregation von <xref:System.ServiceModel.IExtension%601>-Objekten. <xref:System.ServiceModel.IExtension%601>-Objekte sind durch die folgende Schnittstelle gekennzeichnet:  
  
```  
public interface IExtension<T>  
where T : IExtensibleObject<T>  
{  
    void Attach(T owner);  
    void Detach(T owner);  
}  
```  
  
 Die Typbeschränkung stellt sicher, dass Erweiterungen nur für Klassen definiert werden können, für die <xref:System.ServiceModel.IExtensibleObject%601> gilt. <xref:System.ServiceModel.IExtension%601.Attach%2A> und <xref:System.ServiceModel.IExtension%601.Detach%2A> führen die Benachrichtigung über eine Aggregation oder Disaggregation durch.  
  
 Bei Implementierungen können Beschränkungen verwendet werden, wenn sie einem Besitzer hinzugefügt bzw. wenn sie entfernt werden. Sie können zum Beispiel die Entfernung vollständig unmöglich machen, indem Sie das Hinzufügen oder Entfernen von Erweiterungen untersagen, wenn sich der Besitzer oder die Erweiterung in einem bestimmten Zustand befinden, das gleichzeitige Hinzufügen zu mehreren Besitzern untersagen oder nur eine einzelne Hinzufügung gefolgt von einer einzelnen Entfernung zulassen.  
  
 <xref:System.ServiceModel.IExtension%601> impliziert keine Interaktionen mit anderen standardmäßigen verwalteten Schnittstellen. Die <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>-Methode des Besitzerobjekts trennt ihre Erweiterungen in der Regel nicht ab.  
  
 Wenn der Auflistung eine Erweiterung hinzugefügt wird, wird <xref:System.ServiceModel.IExtension%601.Attach%2A> aufgerufen, bevor die Erweiterung in die Auflistung aufgenommen wird. Wenn eine Erweiterung aus der Auflistung entfernt wird, wird nach der Entfernung <xref:System.ServiceModel.IExtension%601.Detach%2A> aufgerufen. Dies bedeutet (vorausgesetzt, es erfolgt eine entsprechende Synchronisierung), dass eine Erweiterung nur dann sicher in einer Auflistung enthalten ist, wenn sie sich zwischen den Zuständen <xref:System.ServiceModel.IExtension%601.Attach%2A> und <xref:System.ServiceModel.IExtension%601.Detach%2A> befindet.  
  
 Für das Objekt, das an <xref:System.ServiceModel.IExtensionCollection%601.FindAll%2A> oder <xref:System.ServiceModel.IExtensionCollection%601.Find%2A> übergeben wird, muss nicht <xref:System.ServiceModel.IExtension%601> gelten (beispielsweise können Sie jedes Objekt übergeben), aber bei der zurückgegebenen Erweiterung handelt es sich um <xref:System.ServiceModel.IExtension%601>.  
  
 Wenn keine Erweiterung in der Auflistung ein <xref:System.ServiceModel.IExtension%601>, <xref:System.ServiceModel.IExtensionCollection%601.Find%2A> gibt null zurück, und <xref:System.ServiceModel.IExtensionCollection%601.FindAll%2A> eine leere Auflistung zurück. Wenn mehrere Erweiterungen <xref:System.ServiceModel.IExtension%601> implementieren, gibt <xref:System.ServiceModel.IExtensionCollection%601.Find%2A> eine davon zurück. Der von <xref:System.ServiceModel.IExtensionCollection%601.FindAll%2A> zurückgegebene Wert ist eine Momentaufnahme.
  
 Es gibt zwei Hauptszenarios. Beim ersten Szenario wird die <xref:System.ServiceModel.IExtensibleObject%601.Extensions%2A>-Eigenschaft als typbasiertes Wörterbuch verwendet, um den Zustand für ein Objekt einzufügen und auf diese Weise eine andere Komponente in die Lage zu versetzen, anhand des Typs danach zu suchen.  
  
 Beim zweiten Szenario werden die Eigenschaften <xref:System.ServiceModel.IExtension%601.Attach%2A> und <xref:System.ServiceModel.IExtension%601.Detach%2A> verwendet, um einem Objekt die Teilnahme am benutzerdefinierten Verhalten zu ermöglichen, zum Beispiel das Registrieren von Ereignissen, Beobachten von Zustandsübergängen usw.  
  
 Die <xref:System.ServiceModel.IExtensionCollection%601>-Schnittstelle ist eine Auflistung von <xref:System.ServiceModel.IExtension%601>-Objekten, für die der Abruf von <xref:System.ServiceModel.IExtension%601> anhand des Typs zulässig ist. <xref:System.ServiceModel.IExtensionCollection%601.Find%2A?displayProperty=nameWithType> gibt das zuletzt hinzugefügte Objekt zurück, das eine <xref:System.ServiceModel.IExtension%601> dieses Typs ist.  
  
### <a name="extensible-objects-in-windows-communication-foundation"></a>Erweiterbare Objekte in Windows Communication Foundation  
 Es gibt vier erweiterbare Objekte in der Windows Communication Foundation (WCF):  
  
-   <xref:System.ServiceModel.ServiceHostBase> – Dies ist die Basisklasse für den Host des Dienstes.  Sie können die Erweiterungen dieser Klasse verwenden, um das Verhalten von <xref:System.ServiceModel.ServiceHostBase> selbst zu erweitern oder um den Zustand für die Dienste einzeln zu speichern.  
  
-   <xref:System.ServiceModel.InstanceContext> – Diese Klasse verbindet eine Instanz des Diensttyps mit der Dienstlaufzeit.  Sie enthält Informationen zu der Instanz sowie einen Verweis auf den <xref:System.ServiceModel.InstanceContext>, der <xref:System.ServiceModel.ServiceHostBase> enthält. Sie können die Erweiterungen dieser Klasse verwenden, um das Verhalten von <xref:System.ServiceModel.InstanceContext> zu erweitern oder um den Zustand für die Dienste einzeln zu speichern.  
  
-   <xref:System.ServiceModel.OperationContext> – Diese Klasse stellt die Vorgangsinformationen dar, die die Laufzeit für jeden Vorgang aufzeichnet.  Dazu gehören auch Informationen wie Header von eingehenden Nachrichten, Eigenschaften von eingehenden Nachrichten, die eingehende Sicherheitsidentität und andere Informationen.  Erweiterungen dieser Klasse können entweder das Verhalten des <xref:System.ServiceModel.OperationContext> erweitern oder den Zustand für jeden Vorgang einzeln speichern.  
  
-   <xref:System.ServiceModel.IContextChannel> – Diese Schnittstelle ermöglicht die Untersuchung der einzelnen Zustände für die Kanäle und Proxys, die von der WCF-Laufzeit erstellt.  Erweiterungen dieser Klasse können entweder das Verhalten des <xref:System.ServiceModel.IClientChannel> erweitern oder das Verhalten verwenden, um den Zustand für jeden Kanal einzeln zu speichern.  
  
-  
  
 Das folgende Codebeispiel zeigt die Verwendung einer einfachen Erweiterung zum Verfolgen von <xref:System.ServiceModel.InstanceContext>-Objekten.  
  
 [!code-csharp[IInstanceContextInitializer#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/iinstancecontextinitializer/cs/initializer.cs#1)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.IExtensibleObject%601>  
 <xref:System.ServiceModel.IExtension%601>  
 <xref:System.ServiceModel.IExtensionCollection%601>
