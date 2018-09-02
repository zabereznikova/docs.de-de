---
title: 'Beispiel: Behandeln von Ausnahmen beim Binden von Daten'
ms.date: 03/30/2017
ms.assetid: bd63ed96-9853-46dc-ade5-7bd1b0f39110
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 89e7a0929bd5f07c5a1986d885984332d692d3a9
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43415878"
---
# <a name="example-handling-exceptions-when-binding-data"></a><span data-ttu-id="c42b7-102">Beispiel: Behandeln von Ausnahmen beim Binden von Daten</span><span class="sxs-lookup"><span data-stu-id="c42b7-102">Example: Handling Exceptions When Binding Data</span></span>
> [!NOTE]
>  <span data-ttu-id="c42b7-103">Dieses Thema bezieht sich auf die .NET Native Developer Preview, ein Vorabrelease der Software.</span><span class="sxs-lookup"><span data-stu-id="c42b7-103">This topic refers to the .NET Native Developer Preview, which is pre-release software.</span></span> <span data-ttu-id="c42b7-104">Sie können die Vorschau von der [Microsoft Connect-Website](https://go.microsoft.com/fwlink/?LinkId=394611) herunterladen (Registrierung erforderlich).</span><span class="sxs-lookup"><span data-stu-id="c42b7-104">You can download the preview from the [Microsoft Connect website](https://go.microsoft.com/fwlink/?LinkId=394611) (requires registration).</span></span>  
  
 <span data-ttu-id="c42b7-105">Im folgenden Beispiel wird veranschaulicht, wie eine [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md)-Ausnahme behoben wird, die ausgelöst wird, wenn eine mit der [!INCLUDE[net_native](../../../includes/net-native-md.md)]-Toolkette kompilierte App versucht, Daten zu binden.</span><span class="sxs-lookup"><span data-stu-id="c42b7-105">The following example shows how to resolve a [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) exception that is thrown when an app compiled with the [!INCLUDE[net_native](../../../includes/net-native-md.md)] tool chain tries to bind data.</span></span> <span data-ttu-id="c42b7-106">Hier sind die Ausnahmeinformationen:</span><span class="sxs-lookup"><span data-stu-id="c42b7-106">Here’s the exception information:</span></span>  
  
```  
This operation cannot be carried out as metadata for the following type was removed for performance reasons:   
App.ViewModels.MainPageVM  
```  
  
 <span data-ttu-id="c42b7-107">Hier ist die zugehörige Aufrufliste:</span><span class="sxs-lookup"><span data-stu-id="c42b7-107">Here's the associated call stack:</span></span>  
  
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
  
## <a name="what-was-the-app-doing"></a><span data-ttu-id="c42b7-108">Was hat die App gerade getan?</span><span class="sxs-lookup"><span data-stu-id="c42b7-108">What was the app doing?</span></span>  
 <span data-ttu-id="c42b7-109">An der Basis des Stapels zeigen Frames aus dem Namespace [Windows.UI.Xaml](https://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.aspx) an, dass die XAML-Rendering-Engine ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="c42b7-109">At the base of the stack, frames from the [Windows.UI.Xaml](https://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.aspx) namespace indicate that the XAML rendering engine was running.</span></span>   <span data-ttu-id="c42b7-110">Die Verwendung der <xref:System.Reflection.PropertyInfo.GetValue%2A?displayProperty=nameWithType>-Methode weist auf einen reflektionsbasierten Abruf des Werts einer Eigenschaft für den Typ hin, dessen Metadaten entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="c42b7-110">The use of the <xref:System.Reflection.PropertyInfo.GetValue%2A?displayProperty=nameWithType> method indicates a reflection-based lookup of a property’s value on the type whose metadata was removed.</span></span>  
  
 <span data-ttu-id="c42b7-111">Der erste Schritt beim Bereitstellen einer Metadatendirektive wäre, `serialize`-Metadaten für den Typ hinzuzufügen, damit auf alle seine Eigenschaften zugegriffen werden kann:</span><span class="sxs-lookup"><span data-stu-id="c42b7-111">The first step in providing a metadata directive would be to add `serialize` metadata for the type so that its properties are all accessible:</span></span>  
  
```xml  
<Type Name="App.ViewModels.MainPageVM" Serialize="Required Public" />  
```  
  
## <a name="is-this-an-isolated-case"></a><span data-ttu-id="c42b7-112">Handelt es sich um einen Einzelfall?</span><span class="sxs-lookup"><span data-stu-id="c42b7-112">Is this an isolated case?</span></span>  
 <span data-ttu-id="c42b7-113">Wenn die Datenbindung in diesem Szenario unvollständige Metadaten für ein `ViewModel` aufweist, kann dies auch für andere gelten.</span><span class="sxs-lookup"><span data-stu-id="c42b7-113">In this scenario, if data binding has incomplete metadata for one `ViewModel`, it may for others, too.</span></span>  <span data-ttu-id="c42b7-114">Wenn der Code so strukturiert ist, dass sich alle Ansichtsmodelle der App im `App.ViewModels`-Namespace befinden, können Sie eine allgemeinere Laufzeitdirektive verwenden:</span><span class="sxs-lookup"><span data-stu-id="c42b7-114">If the code is structured in a way that the app’s view models are all in the `App.ViewModels` namespace, you could use a more general runtime directive:</span></span>  
  
```xml  
<Namespace Name="App.ViewModels " Serialize="Required Public" />  
```  
  
## <a name="could-the-code-be-rewritten-to-not-use-reflection"></a><span data-ttu-id="c42b7-115">Könnte der Code so umgeschrieben werden, dass keine Reflektion verwendet wird?</span><span class="sxs-lookup"><span data-stu-id="c42b7-115">Could the code be rewritten to not use reflection?</span></span>  
 <span data-ttu-id="c42b7-116">Da bei der Datenbindung Reflektion in starkem Maße benötigt wird, ist das Ändern des Codes zur Vermeidung von Reflektion nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="c42b7-116">Because data binding is reflection-intensive, changing the code to avoid reflection isn’t feasible.</span></span>  
  
 <span data-ttu-id="c42b7-117">Es gibt jedoch Möglichkeiten zum Angeben des `ViewModel` auf der XAML-Seite, damit die Toolkette Eigenschaftenbindungen zur Kompilierungszeit den korrekten Typ zuordnen und die Metadaten ohne Verwendung einer Laufzeitdirektive beibehalten kann.</span><span class="sxs-lookup"><span data-stu-id="c42b7-117">However, there are ways to specify the `ViewModel` to the XAML page so that the tool chain can associate property bindings with the correct type at compile time and keep the metadata without using a runtime directive.</span></span>  <span data-ttu-id="c42b7-118">Sie können zum Beispiel das Attribut [Windows.UI.Xaml.Data.BindableAttribute](https://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.data.bindableattribute.aspx) auf Eigenschaften anwenden.</span><span class="sxs-lookup"><span data-stu-id="c42b7-118">For example, you could apply the [Windows.UI.Xaml.Data.BindableAttribute](https://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.data.bindableattribute.aspx) attribute on properties.</span></span> <span data-ttu-id="c42b7-119">Dies bewirkt, dass der XAML-Compiler die erforderlichen Nachschlageinformationen generiert, und vermeidet die Erfordernis einer Laufzeitanweisung in der Datei Default.rd.xml.</span><span class="sxs-lookup"><span data-stu-id="c42b7-119">This causes the XAML compiler to generate the required lookup information and avoids requiring a runtime directive in the Default.rd.xml file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c42b7-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c42b7-120">See Also</span></span>  
 [<span data-ttu-id="c42b7-121">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="c42b7-121">Getting Started</span></span>](../../../docs/framework/net-native/getting-started-with-net-native.md)  
 [<span data-ttu-id="c42b7-122">Example: Troubleshooting Dynamic Programming (Beispiel: Problembehandlung bei dynamischer Programmierung)</span><span class="sxs-lookup"><span data-stu-id="c42b7-122">Example: Troubleshooting Dynamic Programming</span></span>](../../../docs/framework/net-native/example-troubleshooting-dynamic-programming.md)
