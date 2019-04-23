---
title: 'Beispiel: Behandeln von Ausnahmen beim Binden von Daten'
ms.date: 03/30/2017
ms.assetid: bd63ed96-9853-46dc-ade5-7bd1b0f39110
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 25b2117de40bbe7ba36fab028526116fc01ae09b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59199894"
---
# <a name="example-handling-exceptions-when-binding-data"></a>Beispiel: Behandeln von Ausnahmen beim Binden von Daten
> [!NOTE]
>  Dieses Thema bezieht sich auf die .NET Native Developer Preview, ein Vorabrelease der Software. Sie können die Vorschau von der [Microsoft Connect-Website](https://go.microsoft.com/fwlink/?LinkId=394611) herunterladen (Registrierung erforderlich).  
  
 Im folgenden Beispiel wird veranschaulicht, wie eine [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md)-Ausnahme behoben wird, die ausgelöst wird, wenn eine mit der [!INCLUDE[net_native](../../../includes/net-native-md.md)]-Toolkette kompilierte App versucht, Daten zu binden. Hier sind die Ausnahmeinformationen:  
  
```  
This operation cannot be carried out as metadata for the following type was removed for performance reasons:   
App.ViewModels.MainPageVM  
```  
  
 Hier ist die zugehörige Aufrufliste:  
  
```  
Reflection::Execution::ReflectionDomainSetupImplementation.CreateNonInvokabilityException+0x238  
Reflection::Core::ReflectionDomain.CreateNonInvokabilityException+0x2e  
Reflection::Core::Execution::ExecutionEnvironment.+0x316  
System::Reflection::Runtime::PropertyInfos::RuntimePropertyInfo.GetValue+0x1cb  
System::Reflection::PropertyInfo.GetValue+0x22  
System::Runtime::InteropServices::WindowsRuntime::CustomPropertyImpl.GetValue+0x42  
App!$66_Interop::McgNative.Func_IInspectable_IInspectable+0x158  
App!$66_Interop::McgNative::__vtable_Windows_UI_Xaml_Data__ICustomProperty.GetValue__STUB+0x46  
Windows_UI_Xaml!DirectUI::PropertyProviderPropertyAccess::GetValue+0x3f   
Windows_UI_Xaml!DirectUI::PropertyAccessPathStep::GetValue+0x31   
Windows_UI_Xaml!DirectUI::PropertyPathListener::ConnectPathStep+0x113  
```  
  
## <a name="what-was-the-app-doing"></a>Was hat die App gerade getan?  
 Klicken Sie auf der Basis des Stapels, frames, aus der <xref:Windows.UI.Xaml?displayProperty=nameWithType> Namespace anzugeben, dass die XAML-Rendering-Engine ausgeführt wurde.   Die Verwendung der <xref:System.Reflection.PropertyInfo.GetValue%2A?displayProperty=nameWithType>-Methode weist auf einen reflektionsbasierten Abruf des Werts einer Eigenschaft für den Typ hin, dessen Metadaten entfernt wurden.  
  
 Der erste Schritt beim Bereitstellen einer Metadatendirektive wäre, `serialize`-Metadaten für den Typ hinzuzufügen, damit auf alle seine Eigenschaften zugegriffen werden kann:  
  
```xml  
<Type Name="App.ViewModels.MainPageVM" Serialize="Required Public" />  
```  
  
## <a name="is-this-an-isolated-case"></a>Handelt es sich um einen Einzelfall?  
 Wenn die Datenbindung in diesem Szenario unvollständige Metadaten für ein `ViewModel` aufweist, kann dies auch für andere gelten.  Wenn der Code so strukturiert ist, dass sich alle Ansichtsmodelle der App im `App.ViewModels`-Namespace befinden, können Sie eine allgemeinere Laufzeitanweisung verwenden:  
  
```xml  
<Namespace Name="App.ViewModels " Serialize="Required Public" />  
```  
  
## <a name="could-the-code-be-rewritten-to-not-use-reflection"></a>Könnte der Code so umgeschrieben werden, dass keine Reflektion verwendet wird?  
 Da bei der Datenbindung Reflektion in starkem Maße benötigt wird, ist das Ändern des Codes zur Vermeidung von Reflektion nicht möglich.  
  
 Es gibt jedoch Möglichkeiten zum Angeben des `ViewModel` auf der XAML-Seite, damit die Toolkette Eigenschaftenbindungen zur Kompilierungszeit den korrekten Typ zuordnen und die Metadaten ohne Verwendung einer Laufzeitanweisung beibehalten kann.  Sie können z. B. Anwenden der <xref:Windows.UI.Xaml.Data.BindableAttribute?displayProperty=nameWithType> Attribut auf Eigenschaften. Dies bewirkt, dass der XAML-Compiler die erforderlichen Nachschlageinformationen generiert, und vermeidet die Erfordernis einer Laufzeitanweisung in der Datei Default.rd.xml.  
  
## <a name="see-also"></a>Siehe auch

- [Erste Schritte](../../../docs/framework/net-native/getting-started-with-net-native.md)
- [Anpassen von mit VSTU Problembehandlung bei dynamischer Programmierung](../../../docs/framework/net-native/example-troubleshooting-dynamic-programming.md)
