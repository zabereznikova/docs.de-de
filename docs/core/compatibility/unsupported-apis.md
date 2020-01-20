---
title: Nicht unterstützte APIs in .NET Core
description: Erfahren Sie, welche APIs aus .NET Framework immer eine Ausnahme in .NET Core auslösen.
ms.date: 12/23/2019
ms.openlocfilehash: 0cb533f10d53fd3d287265032e3de13c242a8ae0
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901343"
---
# <a name="apis-that-always-throw-exceptions-on-net-core"></a><span data-ttu-id="7e9fb-103">APIs, die in .NET Core immer Ausnahmen auslösen</span><span class="sxs-lookup"><span data-stu-id="7e9fb-103">APIs that always throw exceptions on .NET Core</span></span>

<span data-ttu-id="7e9fb-104">Die folgenden APIs lösen bei der Ausführung von .NET Core auf der angegebenen Plattform immer eine <xref:System.PlatformNotSupportedException> aus.</span><span class="sxs-lookup"><span data-stu-id="7e9fb-104">The following APIs will always through a <xref:System.PlatformNotSupportedException> when run on .NET Core on the specified platform.</span></span>

<span data-ttu-id="7e9fb-105">In diesem Artikel werden die betroffenen API-Member nach Namespace organisiert.</span><span class="sxs-lookup"><span data-stu-id="7e9fb-105">This article organizes the affected API members by namespace.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="7e9fb-106">Dies ist nicht die endgültige Fassung dieses Artikels.</span><span class="sxs-lookup"><span data-stu-id="7e9fb-106">This article is a work-in-progress.</span></span> <span data-ttu-id="7e9fb-107">Er enthält keine vollständige Liste der APIs, die Ausnahmen in .NET Core auslösen.</span><span class="sxs-lookup"><span data-stu-id="7e9fb-107">It is not a complete list of APIs that throw exceptions on .NET Core.</span></span>
> - <span data-ttu-id="7e9fb-108">In diesem Artikel sind die expliziten Schnittstellenimplementierungen für die binäre Serialisierung, die in .NET Core eine Ausnahme auslösen, nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="7e9fb-108">This article does not include the explicit interface implementations for binary serialization that throw on .NET Core.</span></span> <span data-ttu-id="7e9fb-109">Weitere Informationen finden Sie unter [Binäre Serialisierung](../../standard/serialization/binary-serialization.md#net-core).</span><span class="sxs-lookup"><span data-stu-id="7e9fb-109">For more information, see [Binary serialization in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span></span>

## <a name="system"></a><span data-ttu-id="7e9fb-110">System</span><span class="sxs-lookup"><span data-stu-id="7e9fb-110">System</span></span>

| <span data-ttu-id="7e9fb-111">Member</span><span class="sxs-lookup"><span data-stu-id="7e9fb-111">Member</span></span> | <span data-ttu-id="7e9fb-112">Plattform</span><span class="sxs-lookup"><span data-stu-id="7e9fb-112">Platform</span></span> |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-113">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-113">All</span></span> |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-114">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-114">All</span></span> |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-115">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-115">Linux and macOS</span></span> |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-116">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-116">Linux and macOS</span></span> |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-117">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-117">All</span></span> |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-118">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-118">All</span></span> |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-119">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-119">All</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-120">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-120">All</span></span> |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-121">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-121">All</span></span> |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-122">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-122">All</span></span> |

## <a name="systemcodedomcompiler"></a><span data-ttu-id="7e9fb-123">System.CodeDom.Compiler</span><span class="sxs-lookup"><span data-stu-id="7e9fb-123">System.CodeDom.Compiler</span></span>

| <span data-ttu-id="7e9fb-124">Member</span><span class="sxs-lookup"><span data-stu-id="7e9fb-124">Member</span></span> | <span data-ttu-id="7e9fb-125">Plattform</span><span class="sxs-lookup"><span data-stu-id="7e9fb-125">Platform</span></span> |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-126">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-126">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-127">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-127">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-128">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-128">All</span></span> |

## <a name="systemcollectionsspecialized"></a><span data-ttu-id="7e9fb-129">System.Collections.Specialized</span><span class="sxs-lookup"><span data-stu-id="7e9fb-129">System.Collections.Specialized</span></span>

| <span data-ttu-id="7e9fb-130">Member</span><span class="sxs-lookup"><span data-stu-id="7e9fb-130">Member</span></span> | <span data-ttu-id="7e9fb-131">Plattform</span><span class="sxs-lookup"><span data-stu-id="7e9fb-131">Platform</span></span> |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-132">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-132">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-133">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-133">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-134">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-134">All</span></span> |

## <a name="systemconfiguration"></a><span data-ttu-id="7e9fb-135">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="7e9fb-135">System.Configuration</span></span>

| <span data-ttu-id="7e9fb-136">Member</span><span class="sxs-lookup"><span data-stu-id="7e9fb-136">Member</span></span> | <span data-ttu-id="7e9fb-137">Plattform</span><span class="sxs-lookup"><span data-stu-id="7e9fb-137">Platform</span></span> |
| - | - |
| <span data-ttu-id="7e9fb-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (alle Member)</span><span class="sxs-lookup"><span data-stu-id="7e9fb-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (all members)</span></span> | <span data-ttu-id="7e9fb-139">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-139">All</span></span> |

## <a name="systemconsole"></a><span data-ttu-id="7e9fb-140">System.Console</span><span class="sxs-lookup"><span data-stu-id="7e9fb-140">System.Console</span></span>

| <span data-ttu-id="7e9fb-141">Member</span><span class="sxs-lookup"><span data-stu-id="7e9fb-141">Member</span></span> | <span data-ttu-id="7e9fb-142">Plattform</span><span class="sxs-lookup"><span data-stu-id="7e9fb-142">Platform</span></span> |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-143">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-143">Linux and macOS</span></span> |
| <span data-ttu-id="7e9fb-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="7e9fb-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7e9fb-145">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-145">Linux and macOS</span></span> |
| <span data-ttu-id="7e9fb-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="7e9fb-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7e9fb-147">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-147">Linux and macOS</span></span> |
| <span data-ttu-id="7e9fb-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="7e9fb-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7e9fb-149">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-149">Linux and macOS</span></span> |
| <span data-ttu-id="7e9fb-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (nur „get“)</span><span class="sxs-lookup"><span data-stu-id="7e9fb-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="7e9fb-151">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-151">Linux and macOS</span></span> |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-152">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-152">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-153">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-153">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-154">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-154">Linux and macOS</span></span> |
| <span data-ttu-id="7e9fb-155"><xref:System.Console.Title?displayProperty=nameWithType> (nur „get“)</span><span class="sxs-lookup"><span data-stu-id="7e9fb-155"><xref:System.Console.Title?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="7e9fb-156">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-156">Linux and macOS</span></span> |
| <span data-ttu-id="7e9fb-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="7e9fb-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7e9fb-158">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-158">Linux and macOS</span></span> |
| <span data-ttu-id="7e9fb-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="7e9fb-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7e9fb-160">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-160">Linux and macOS</span></span> |
| <span data-ttu-id="7e9fb-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="7e9fb-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7e9fb-162">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-162">Linux and macOS</span></span> |
| <span data-ttu-id="7e9fb-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="7e9fb-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7e9fb-164">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-164">Linux and macOS</span></span> |

## <a name="systemdatacommon"></a><span data-ttu-id="7e9fb-165">System.Data.Common</span><span class="sxs-lookup"><span data-stu-id="7e9fb-165">System.Data.Common</span></span>

| <span data-ttu-id="7e9fb-166">Member</span><span class="sxs-lookup"><span data-stu-id="7e9fb-166">Member</span></span> | <span data-ttu-id="7e9fb-167">Plattform</span><span class="sxs-lookup"><span data-stu-id="7e9fb-167">Platform</span></span> |
| - | - |
| <span data-ttu-id="7e9fb-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (löst <xref:System.NotSupportedException> aus)</span><span class="sxs-lookup"><span data-stu-id="7e9fb-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (throws <xref:System.NotSupportedException>)</span></span> | <span data-ttu-id="7e9fb-169">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-169">All</span></span> |

## <a name="systemdiagnosticsprocess"></a><span data-ttu-id="7e9fb-170">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="7e9fb-170">System.Diagnostics.Process</span></span>

| <span data-ttu-id="7e9fb-171">Member</span><span class="sxs-lookup"><span data-stu-id="7e9fb-171">Member</span></span> | <span data-ttu-id="7e9fb-172">Plattform</span><span class="sxs-lookup"><span data-stu-id="7e9fb-172">Platform</span></span> |
| - | - |
| <span data-ttu-id="7e9fb-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="7e9fb-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7e9fb-174">Linux</span><span class="sxs-lookup"><span data-stu-id="7e9fb-174">Linux</span></span> |
| <span data-ttu-id="7e9fb-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="7e9fb-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7e9fb-176">Linux</span><span class="sxs-lookup"><span data-stu-id="7e9fb-176">Linux</span></span> |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-177">macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-177">macOS</span></span> |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-178">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-178">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-179">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-179">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-180">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-180">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-181">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-181">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-182">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-182">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-183">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-183">Linux and macOS</span></span> |
| <span data-ttu-id="7e9fb-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="7e9fb-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7e9fb-185">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-185">Linux and macOS</span></span> |
| <span data-ttu-id="7e9fb-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (nur „get“)</span><span class="sxs-lookup"><span data-stu-id="7e9fb-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="7e9fb-187">macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-187">macOS</span></span> |
| <span data-ttu-id="7e9fb-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="7e9fb-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7e9fb-189">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-189">Linux and macOS</span></span> |

## <a name="systemio"></a><span data-ttu-id="7e9fb-190">System.IO</span><span class="sxs-lookup"><span data-stu-id="7e9fb-190">System.IO</span></span>

| <span data-ttu-id="7e9fb-191">Member</span><span class="sxs-lookup"><span data-stu-id="7e9fb-191">Member</span></span> | <span data-ttu-id="7e9fb-192">Plattform</span><span class="sxs-lookup"><span data-stu-id="7e9fb-192">Platform</span></span> |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-193">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-193">All</span></span> |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-194">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-194">All</span></span> |

## <a name="systemiopipes"></a><span data-ttu-id="7e9fb-195">System.IO.Pipes</span><span class="sxs-lookup"><span data-stu-id="7e9fb-195">System.IO.Pipes</span></span>

| <span data-ttu-id="7e9fb-196">Member</span><span class="sxs-lookup"><span data-stu-id="7e9fb-196">Member</span></span> | <span data-ttu-id="7e9fb-197">Plattform</span><span class="sxs-lookup"><span data-stu-id="7e9fb-197">Platform</span></span> |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-198">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-198">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-199">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-199">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-200">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-200">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-201">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-201">Linux and macOS</span></span> |
| <span data-ttu-id="7e9fb-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="7e9fb-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7e9fb-203">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-203">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-204">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-204">Linux and macOS</span></span> |

## <a name="systemmedia"></a><span data-ttu-id="7e9fb-205">System. Media</span><span class="sxs-lookup"><span data-stu-id="7e9fb-205">System.Media</span></span>

| <span data-ttu-id="7e9fb-206">Member</span><span class="sxs-lookup"><span data-stu-id="7e9fb-206">Member</span></span> | <span data-ttu-id="7e9fb-207">Plattform</span><span class="sxs-lookup"><span data-stu-id="7e9fb-207">Platform</span></span> |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-208">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-208">All</span></span> |

## <a name="systemnet"></a><span data-ttu-id="7e9fb-209">System.Net</span><span class="sxs-lookup"><span data-stu-id="7e9fb-209">System.Net</span></span>

| <span data-ttu-id="7e9fb-210">Member</span><span class="sxs-lookup"><span data-stu-id="7e9fb-210">Member</span></span> | <span data-ttu-id="7e9fb-211">Plattform</span><span class="sxs-lookup"><span data-stu-id="7e9fb-211">Platform</span></span> |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-212">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-212">All</span></span> |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-213">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-213">All</span></span> |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-214">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-214">All</span></span> |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-215">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-215">All</span></span> |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-216">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-216">All</span></span> |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-217">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-217">All</span></span> |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-218">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-218">All</span></span> |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-219">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-219">All</span></span> |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-220">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-220">All</span></span> |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-221">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-221">All</span></span> |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-222">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-222">All</span></span> |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-223">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-223">All</span></span> |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-224">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-224">All</span></span> |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-225">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-225">All</span></span> |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-226">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-226">All</span></span> |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-227">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-227">All</span></span> |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-228">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-228">All</span></span> |

## <a name="systemnetnetworkinformation"></a><span data-ttu-id="7e9fb-229">System.Net.NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="7e9fb-229">System.Net.NetworkInformation</span></span>

| <span data-ttu-id="7e9fb-230">Member</span><span class="sxs-lookup"><span data-stu-id="7e9fb-230">Member</span></span> | <span data-ttu-id="7e9fb-231">Plattform</span><span class="sxs-lookup"><span data-stu-id="7e9fb-231">Platform</span></span> |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-232">Windows (UWP)</span><span class="sxs-lookup"><span data-stu-id="7e9fb-232">Windows (UWP)</span></span> |

## <a name="systemnetsockets"></a><span data-ttu-id="7e9fb-233">System.Net.Sockets</span><span class="sxs-lookup"><span data-stu-id="7e9fb-233">System.Net.Sockets</span></span>

| <span data-ttu-id="7e9fb-234">Member</span><span class="sxs-lookup"><span data-stu-id="7e9fb-234">Member</span></span> | <span data-ttu-id="7e9fb-235">Plattform</span><span class="sxs-lookup"><span data-stu-id="7e9fb-235">Platform</span></span> |
| - | - |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-236">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-236">All</span></span> |

## <a name="systemnetwebsockets"></a><span data-ttu-id="7e9fb-237">System.Net.WebSockets</span><span class="sxs-lookup"><span data-stu-id="7e9fb-237">System.Net.WebSockets</span></span>

| <span data-ttu-id="7e9fb-238">Member</span><span class="sxs-lookup"><span data-stu-id="7e9fb-238">Member</span></span> | <span data-ttu-id="7e9fb-239">Plattform</span><span class="sxs-lookup"><span data-stu-id="7e9fb-239">Platform</span></span> |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-240">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-240">All</span></span> |

## <a name="systemreflection"></a><span data-ttu-id="7e9fb-241">System.Reflection</span><span class="sxs-lookup"><span data-stu-id="7e9fb-241">System.Reflection</span></span>

| <span data-ttu-id="7e9fb-242">Member</span><span class="sxs-lookup"><span data-stu-id="7e9fb-242">Member</span></span> | <span data-ttu-id="7e9fb-243">Plattform</span><span class="sxs-lookup"><span data-stu-id="7e9fb-243">Platform</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-244">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-244">All</span></span> |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-245">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-245">All</span></span> |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-246">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-246">All</span></span> |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-247">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-247">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-248">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-248">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-249">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-249">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-250">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-250">All</span></span> |

## <a name="systemruntimecompilerservices"></a><span data-ttu-id="7e9fb-251">System.Runtime.CompilerServices</span><span class="sxs-lookup"><span data-stu-id="7e9fb-251">System.Runtime.CompilerServices</span></span>

| <span data-ttu-id="7e9fb-252">Member</span><span class="sxs-lookup"><span data-stu-id="7e9fb-252">Member</span></span> | <span data-ttu-id="7e9fb-253">Plattform</span><span class="sxs-lookup"><span data-stu-id="7e9fb-253">Platform</span></span> |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-254">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-254">All</span></span> |

## <a name="systemruntimeinteropservices"></a><span data-ttu-id="7e9fb-255">System.Runtime.InteropServices</span><span class="sxs-lookup"><span data-stu-id="7e9fb-255">System.Runtime.InteropServices</span></span>

| <span data-ttu-id="7e9fb-256">Member</span><span class="sxs-lookup"><span data-stu-id="7e9fb-256">Member</span></span> | <span data-ttu-id="7e9fb-257">Plattform</span><span class="sxs-lookup"><span data-stu-id="7e9fb-257">Platform</span></span> |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-258">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-258">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-259">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-259">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-260">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-260">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-261">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-261">All</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-262">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-262">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-263">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-263">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-264">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-264">Linux and macOS</span></span> |

## <a name="systemruntimeserialization"></a><span data-ttu-id="7e9fb-265">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="7e9fb-265">System.Runtime.Serialization</span></span>

| <span data-ttu-id="7e9fb-266">Member</span><span class="sxs-lookup"><span data-stu-id="7e9fb-266">Member</span></span> | <span data-ttu-id="7e9fb-267">Plattform</span><span class="sxs-lookup"><span data-stu-id="7e9fb-267">Platform</span></span> |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-268">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-268">All</span></span> |

## <a name="systemsecurity"></a><span data-ttu-id="7e9fb-269">System.Security</span><span class="sxs-lookup"><span data-stu-id="7e9fb-269">System.Security</span></span>

| <span data-ttu-id="7e9fb-270">Member</span><span class="sxs-lookup"><span data-stu-id="7e9fb-270">Member</span></span> | <span data-ttu-id="7e9fb-271">Plattform</span><span class="sxs-lookup"><span data-stu-id="7e9fb-271">Platform</span></span> |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-272">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-272">All</span></span> |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-273">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-273">All</span></span> |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-274">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-274">All</span></span> |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-275">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-275">All</span></span> |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-276">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-276">All</span></span> |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-277">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-277">All</span></span> |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-278">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-278">All</span></span> |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-279">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-279">All</span></span> |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-280">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-280">All</span></span> |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-281">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-281">All</span></span> |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-282">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-282">All</span></span> |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-283">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-283">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-284">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-284">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-285">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-285">All</span></span> |

## <a name="systemsecurityclaims"></a><span data-ttu-id="7e9fb-286">System.Security.Claims</span><span class="sxs-lookup"><span data-stu-id="7e9fb-286">System.Security.Claims</span></span>

| <span data-ttu-id="7e9fb-287">Member</span><span class="sxs-lookup"><span data-stu-id="7e9fb-287">Member</span></span> | <span data-ttu-id="7e9fb-288">Plattform</span><span class="sxs-lookup"><span data-stu-id="7e9fb-288">Platform</span></span> |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-289">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-289">All</span></span> |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-290">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-290">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-291">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-291">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-292">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-292">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-293">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-293">All</span></span> |

## <a name="systemsecuritycryptography"></a><span data-ttu-id="7e9fb-294">System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="7e9fb-294">System.Security.Cryptography</span></span>

| <span data-ttu-id="7e9fb-295">Member</span><span class="sxs-lookup"><span data-stu-id="7e9fb-295">Member</span></span> | <span data-ttu-id="7e9fb-296">Plattform</span><span class="sxs-lookup"><span data-stu-id="7e9fb-296">Platform</span></span> |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-297">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-297">All</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-298">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-298">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-299">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-299">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-300">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-300">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-301">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-301">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-302">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-302">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-303">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-303">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-304">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-304">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-305">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-305">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-306">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-306">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-307">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-307">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-308">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-308">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-309">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-309">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-310">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-310">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-311">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-311">All</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-312">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-312">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-313">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-313">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-314">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-314">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-315">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-315">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-316">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-316">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-317">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-317">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-318">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-318">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-319">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-319">All</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-320">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-320">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-321">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="7e9fb-321">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-322">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-322">All</span></span> |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-323">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-323">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-324">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-324">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-325">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-325">All</span></span> |

## <a name="systemsecuritycryptographypkcs"></a><span data-ttu-id="7e9fb-326">System.Security.Cryptography.Pkcs</span><span class="sxs-lookup"><span data-stu-id="7e9fb-326">System.Security.Cryptography.Pkcs</span></span>

| <span data-ttu-id="7e9fb-327">Member</span><span class="sxs-lookup"><span data-stu-id="7e9fb-327">Member</span></span> | <span data-ttu-id="7e9fb-328">Plattform</span><span class="sxs-lookup"><span data-stu-id="7e9fb-328">Platform</span></span> |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-329">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-329">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-330">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-330">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-331">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-331">All</span></span> |

## <a name="systemsecuritycryptographyx509certificates"></a><span data-ttu-id="7e9fb-332">System.Security.Cryptography.X509Certificates</span><span class="sxs-lookup"><span data-stu-id="7e9fb-332">System.Security.Cryptography.X509Certificates</span></span>

| <span data-ttu-id="7e9fb-333">Member</span><span class="sxs-lookup"><span data-stu-id="7e9fb-333">Member</span></span> | <span data-ttu-id="7e9fb-334">Plattform</span><span class="sxs-lookup"><span data-stu-id="7e9fb-334">Platform</span></span> |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-335">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-335">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-336">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-336">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-337">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-337">All</span></span> |
| <span data-ttu-id="7e9fb-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="7e9fb-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="7e9fb-339">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-339">All</span></span> |

## <a name="systemsecurityauthenticationextendedprotection"></a><span data-ttu-id="7e9fb-340">System.Security.Authentication.ExtendedProtection</span><span class="sxs-lookup"><span data-stu-id="7e9fb-340">System.Security.Authentication.ExtendedProtection</span></span>

| <span data-ttu-id="7e9fb-341">Member</span><span class="sxs-lookup"><span data-stu-id="7e9fb-341">Member</span></span> | <span data-ttu-id="7e9fb-342">Plattform</span><span class="sxs-lookup"><span data-stu-id="7e9fb-342">Platform</span></span> |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-343">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-343">All</span></span> |

## <a name="systemsecuritypolicy"></a><span data-ttu-id="7e9fb-344">System.Security.Policy</span><span class="sxs-lookup"><span data-stu-id="7e9fb-344">System.Security.Policy</span></span>

| <span data-ttu-id="7e9fb-345">Member</span><span class="sxs-lookup"><span data-stu-id="7e9fb-345">Member</span></span> | <span data-ttu-id="7e9fb-346">Plattform</span><span class="sxs-lookup"><span data-stu-id="7e9fb-346">Platform</span></span> |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-347">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-347">All</span></span> |

## <a name="systemserviceprocessservicecontroller"></a><span data-ttu-id="7e9fb-348">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="7e9fb-348">System.ServiceProcess.ServiceController</span></span>

| <span data-ttu-id="7e9fb-349">Member</span><span class="sxs-lookup"><span data-stu-id="7e9fb-349">Member</span></span> | <span data-ttu-id="7e9fb-350">Plattform</span><span class="sxs-lookup"><span data-stu-id="7e9fb-350">Platform</span></span> |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-351">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-351">All</span></span> |

## <a name="systemtextregularexpressions"></a><span data-ttu-id="7e9fb-352">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="7e9fb-352">System.Text.RegularExpressions</span></span>

| <span data-ttu-id="7e9fb-353">Member</span><span class="sxs-lookup"><span data-stu-id="7e9fb-353">Member</span></span> | <span data-ttu-id="7e9fb-354">Plattform</span><span class="sxs-lookup"><span data-stu-id="7e9fb-354">Platform</span></span> |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-355">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-355">All</span></span> |

## <a name="systemthreading"></a><span data-ttu-id="7e9fb-356">System.Threading</span><span class="sxs-lookup"><span data-stu-id="7e9fb-356">System.Threading</span></span>

| <span data-ttu-id="7e9fb-357">Member</span><span class="sxs-lookup"><span data-stu-id="7e9fb-357">Member</span></span> | <span data-ttu-id="7e9fb-358">Plattform</span><span class="sxs-lookup"><span data-stu-id="7e9fb-358">Platform</span></span> |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-359">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-359">All</span></span> |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-360">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-360">All</span></span> |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-361">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-361">All</span></span> |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-362">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-362">All</span></span> |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-363">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-363">All</span></span> |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-364">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-364">All</span></span> |

## <a name="systemxml"></a><span data-ttu-id="7e9fb-365">System.Xml</span><span class="sxs-lookup"><span data-stu-id="7e9fb-365">System.Xml</span></span>

| <span data-ttu-id="7e9fb-366">Member</span><span class="sxs-lookup"><span data-stu-id="7e9fb-366">Member</span></span> | <span data-ttu-id="7e9fb-367">Plattform</span><span class="sxs-lookup"><span data-stu-id="7e9fb-367">Platform</span></span> |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-368">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-368">All</span></span> |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-369">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-369">All</span></span> |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="7e9fb-370">Alle</span><span class="sxs-lookup"><span data-stu-id="7e9fb-370">All</span></span> |

## <a name="see-also"></a><span data-ttu-id="7e9fb-371">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e9fb-371">See also</span></span>

- [<span data-ttu-id="7e9fb-372">Breaking Changes für die Migration von .NET Framework 3.0 zu .NET Core</span><span class="sxs-lookup"><span data-stu-id="7e9fb-372">Breaking changes for migration from .NET Framework to .NET Core</span></span>](../compatibility/fx-core.md)
- [<span data-ttu-id="7e9fb-373">Binäre Serialisierung in .NET Core</span><span class="sxs-lookup"><span data-stu-id="7e9fb-373">Binary serialization in .NET Core</span></span>](../../standard/serialization/binary-serialization.md#net-core)
- [<span data-ttu-id="7e9fb-374">.NET Portability Analyzer</span><span class="sxs-lookup"><span data-stu-id="7e9fb-374">.NET portability analyzer</span></span>](../../standard/analyzers/portability-analyzer.md)
