---
title: 'Beispiel: Behandeln von Ausnahmen beim Binden von Daten'
ms.date: 03/30/2017
ms.assetid: bd63ed96-9853-46dc-ade5-7bd1b0f39110
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5be728cbeb0c3378bb35765787b299167069f57
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910624"
---
# <a name="example-handling-exceptions-when-binding-data"></a><span data-ttu-id="c649c-102">Beispiel: Behandeln von Ausnahmen beim Binden von Daten</span><span class="sxs-lookup"><span data-stu-id="c649c-102">Example: Handling Exceptions When Binding Data</span></span>
> [!NOTE]
> <span data-ttu-id="c649c-103">Dieses Thema bezieht sich auf die .NET Native Developer Preview, ein Vorabrelease der Software.</span><span class="sxs-lookup"><span data-stu-id="c649c-103">This topic refers to the .NET Native Developer Preview, which is pre-release software.</span></span> <span data-ttu-id="c649c-104">Sie können die Vorschau von der [Microsoft Connect-Website](https://go.microsoft.com/fwlink/?LinkId=394611) herunterladen (Registrierung erforderlich).</span><span class="sxs-lookup"><span data-stu-id="c649c-104">You can download the preview from the [Microsoft Connect website](https://go.microsoft.com/fwlink/?LinkId=394611) (requires registration).</span></span>  
  
 <span data-ttu-id="c649c-105">Das folgende Beispiel zeigt, wie eine [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) -Ausnahme aufgelöst wird, die ausgelöst wird, wenn eine mit der .net Native-Toolkette kompilierte app versucht, Daten zu binden.</span><span class="sxs-lookup"><span data-stu-id="c649c-105">The following example shows how to resolve a [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) exception that is thrown when an app compiled with the .NET Native tool chain tries to bind data.</span></span> <span data-ttu-id="c649c-106">Hier sind die Ausnahmeinformationen:</span><span class="sxs-lookup"><span data-stu-id="c649c-106">Here’s the exception information:</span></span>  
  
```  
This operation cannot be carried out as metadata for the following type was removed for performance reasons:   
App.ViewModels.MainPageVM  
```  
  
 <span data-ttu-id="c649c-107">Hier ist die zugehörige Aufrufliste:</span><span class="sxs-lookup"><span data-stu-id="c649c-107">Here's the associated call stack:</span></span>  
  
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
  
## <a name="what-was-the-app-doing"></a><span data-ttu-id="c649c-108">Was hat die App gerade getan?</span><span class="sxs-lookup"><span data-stu-id="c649c-108">What was the app doing?</span></span>  
 <span data-ttu-id="c649c-109">An der Basis des Stapels geben Frames aus dem <xref:Windows.UI.Xaml?displayProperty=nameWithType> -Namespace an, dass die XAML-Rendering-Engine ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="c649c-109">At the base of the stack, frames from the <xref:Windows.UI.Xaml?displayProperty=nameWithType> namespace indicate that the XAML rendering engine was running.</span></span>   <span data-ttu-id="c649c-110">Die Verwendung der <xref:System.Reflection.PropertyInfo.GetValue%2A?displayProperty=nameWithType>-Methode weist auf einen reflektionsbasierten Abruf des Werts einer Eigenschaft für den Typ hin, dessen Metadaten entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="c649c-110">The use of the <xref:System.Reflection.PropertyInfo.GetValue%2A?displayProperty=nameWithType> method indicates a reflection-based lookup of a property’s value on the type whose metadata was removed.</span></span>  
  
 <span data-ttu-id="c649c-111">Der erste Schritt beim Bereitstellen einer Metadatendirektive wäre, `serialize`-Metadaten für den Typ hinzuzufügen, damit auf alle seine Eigenschaften zugegriffen werden kann:</span><span class="sxs-lookup"><span data-stu-id="c649c-111">The first step in providing a metadata directive would be to add `serialize` metadata for the type so that its properties are all accessible:</span></span>  
  
```xml  
<Type Name="App.ViewModels.MainPageVM" Serialize="Required Public" />  
```  
  
## <a name="is-this-an-isolated-case"></a><span data-ttu-id="c649c-112">Handelt es sich um einen Einzelfall?</span><span class="sxs-lookup"><span data-stu-id="c649c-112">Is this an isolated case?</span></span>  
 <span data-ttu-id="c649c-113">Wenn die Datenbindung in diesem Szenario unvollständige Metadaten für ein `ViewModel` aufweist, kann dies auch für andere gelten.</span><span class="sxs-lookup"><span data-stu-id="c649c-113">In this scenario, if data binding has incomplete metadata for one `ViewModel`, it may for others, too.</span></span>  <span data-ttu-id="c649c-114">Wenn der Code so strukturiert ist, dass sich alle Ansichtsmodelle der App im `App.ViewModels`-Namespace befinden, können Sie eine allgemeinere Laufzeitanweisung verwenden:</span><span class="sxs-lookup"><span data-stu-id="c649c-114">If the code is structured in a way that the app’s view models are all in the `App.ViewModels` namespace, you could use a more general runtime directive:</span></span>  
  
```xml  
<Namespace Name="App.ViewModels " Serialize="Required Public" />  
```  
  
## <a name="could-the-code-be-rewritten-to-not-use-reflection"></a><span data-ttu-id="c649c-115">Könnte der Code so umgeschrieben werden, dass keine Reflektion verwendet wird?</span><span class="sxs-lookup"><span data-stu-id="c649c-115">Could the code be rewritten to not use reflection?</span></span>  
 <span data-ttu-id="c649c-116">Da bei der Datenbindung Reflektion in starkem Maße benötigt wird, ist das Ändern des Codes zur Vermeidung von Reflektion nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="c649c-116">Because data binding is reflection-intensive, changing the code to avoid reflection isn’t feasible.</span></span>  
  
 <span data-ttu-id="c649c-117">Es gibt jedoch Möglichkeiten zum Angeben des `ViewModel` auf der XAML-Seite, damit die Toolkette Eigenschaftenbindungen zur Kompilierungszeit den korrekten Typ zuordnen und die Metadaten ohne Verwendung einer Laufzeitanweisung beibehalten kann.</span><span class="sxs-lookup"><span data-stu-id="c649c-117">However, there are ways to specify the `ViewModel` to the XAML page so that the tool chain can associate property bindings with the correct type at compile time and keep the metadata without using a runtime directive.</span></span>  <span data-ttu-id="c649c-118">Beispielsweise können Sie das <xref:Windows.UI.Xaml.Data.BindableAttribute?displayProperty=nameWithType> -Attribut auf Eigenschaften anwenden.</span><span class="sxs-lookup"><span data-stu-id="c649c-118">For example, you could apply the <xref:Windows.UI.Xaml.Data.BindableAttribute?displayProperty=nameWithType> attribute on properties.</span></span> <span data-ttu-id="c649c-119">Dies bewirkt, dass der XAML-Compiler die erforderlichen Nachschlageinformationen generiert, und vermeidet die Erfordernis einer Laufzeitanweisung in der Datei Default.rd.xml.</span><span class="sxs-lookup"><span data-stu-id="c649c-119">This causes the XAML compiler to generate the required lookup information and avoids requiring a runtime directive in the Default.rd.xml file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c649c-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c649c-120">See also</span></span>

- [<span data-ttu-id="c649c-121">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="c649c-121">Getting Started</span></span>](../../../docs/framework/net-native/getting-started-with-net-native.md)
- [<span data-ttu-id="c649c-122">Anpassen von mit VSTU Problembehandlung bei dynamischer Programmierung</span><span class="sxs-lookup"><span data-stu-id="c649c-122">Example: Troubleshooting Dynamic Programming</span></span>](../../../docs/framework/net-native/example-troubleshooting-dynamic-programming.md)
