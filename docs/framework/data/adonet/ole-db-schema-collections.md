---
title: OLE DB-Schemaauflistungen
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 1ab6426875b73b400a59b7e4cf155615d7472d05
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43514488"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="2f613-102">OLE DB-Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="2f613-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="2f613-103">In diesem Abschnitt wird die Unterstützung von Schemaauflistungen für die ODBC-Anbieter für Microsoft SQL Server, Oracle und Microsoft Jet diskutiert.</span><span class="sxs-lookup"><span data-stu-id="2f613-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="2f613-104">Microsoft SQL Server-OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="2f613-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="2f613-105">Der Microsoft SQL Server OLE DB-Treiber unterstützt neben den allgemeinen schemaauflistungen die folgenden spezifischen schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="2f613-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="2f613-106">Tabellen</span><span class="sxs-lookup"><span data-stu-id="2f613-106">Tables</span></span>  
  
-   <span data-ttu-id="2f613-107">Columns</span><span class="sxs-lookup"><span data-stu-id="2f613-107">Columns</span></span>  
  
-   <span data-ttu-id="2f613-108">Verfahren</span><span class="sxs-lookup"><span data-stu-id="2f613-108">Procedures</span></span>  
  
-   <span data-ttu-id="2f613-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="2f613-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="2f613-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="2f613-110">Catalog</span></span>  
  
-   <span data-ttu-id="2f613-111">Indexes</span><span class="sxs-lookup"><span data-stu-id="2f613-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="2f613-112">Tabellen</span><span class="sxs-lookup"><span data-stu-id="2f613-112">Tables</span></span>  
  
|<span data-ttu-id="2f613-113">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="2f613-113">ColumnName</span></span>|<span data-ttu-id="2f613-114">DataType</span><span class="sxs-lookup"><span data-stu-id="2f613-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2f613-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2f613-115">TABLE_CATALOG</span></span>|<span data-ttu-id="2f613-116">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-116">String</span></span>|  
|<span data-ttu-id="2f613-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2f613-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="2f613-118">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-118">String</span></span>|  
|<span data-ttu-id="2f613-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-119">TABLE_NAME</span></span>|<span data-ttu-id="2f613-120">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-120">String</span></span>|  
|<span data-ttu-id="2f613-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2f613-121">TABLE_TYPE</span></span>|<span data-ttu-id="2f613-122">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-122">String</span></span>|  
|<span data-ttu-id="2f613-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="2f613-123">TABLE_GUID</span></span>|<span data-ttu-id="2f613-124">Guid</span><span class="sxs-lookup"><span data-stu-id="2f613-124">Guid</span></span>|  
|<span data-ttu-id="2f613-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2f613-125">DESCRIPTION</span></span>|<span data-ttu-id="2f613-126">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-126">String</span></span>|  
|<span data-ttu-id="2f613-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="2f613-127">TABLE_PROPID</span></span>|<span data-ttu-id="2f613-128">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-128">Int64</span></span>|  
|<span data-ttu-id="2f613-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="2f613-129">DATE_CREATED</span></span>|<span data-ttu-id="2f613-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="2f613-130">DateTime</span></span>|  
|<span data-ttu-id="2f613-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="2f613-131">DATE_MODIFIED</span></span>|<span data-ttu-id="2f613-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="2f613-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="2f613-133">Columns</span><span class="sxs-lookup"><span data-stu-id="2f613-133">Columns</span></span>  
  
|<span data-ttu-id="2f613-134">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="2f613-134">ColumnName</span></span>|<span data-ttu-id="2f613-135">DataType</span><span class="sxs-lookup"><span data-stu-id="2f613-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2f613-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2f613-136">TABLE_CATALOG</span></span>|<span data-ttu-id="2f613-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-137">String</span></span>|  
|<span data-ttu-id="2f613-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2f613-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="2f613-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-139">String</span></span>|  
|<span data-ttu-id="2f613-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-140">TABLE_NAME</span></span>|<span data-ttu-id="2f613-141">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-141">String</span></span>|  
|<span data-ttu-id="2f613-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-142">COLUMN_NAME</span></span>|<span data-ttu-id="2f613-143">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-143">String</span></span>|  
|<span data-ttu-id="2f613-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="2f613-144">COLUMN_GUID</span></span>|<span data-ttu-id="2f613-145">Guid</span><span class="sxs-lookup"><span data-stu-id="2f613-145">Guid</span></span>|  
|<span data-ttu-id="2f613-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="2f613-146">COLUMN_PROPID</span></span>|<span data-ttu-id="2f613-147">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-147">Int64</span></span>|  
|<span data-ttu-id="2f613-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2f613-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="2f613-149">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-149">Int64</span></span>|  
|<span data-ttu-id="2f613-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="2f613-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="2f613-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="2f613-151">Boolean</span></span>|  
|<span data-ttu-id="2f613-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="2f613-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="2f613-153">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-153">String</span></span>|  
|<span data-ttu-id="2f613-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="2f613-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="2f613-155">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-155">Int64</span></span>|  
|<span data-ttu-id="2f613-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2f613-156">IS_NULLABLE</span></span>|<span data-ttu-id="2f613-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="2f613-157">Boolean</span></span>|  
|<span data-ttu-id="2f613-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2f613-158">DATA_TYPE</span></span>|<span data-ttu-id="2f613-159">Int32</span><span class="sxs-lookup"><span data-stu-id="2f613-159">Int32</span></span>|  
|<span data-ttu-id="2f613-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="2f613-160">TYPE_GUID</span></span>|<span data-ttu-id="2f613-161">Guid</span><span class="sxs-lookup"><span data-stu-id="2f613-161">Guid</span></span>|  
|<span data-ttu-id="2f613-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2f613-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="2f613-163">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-163">Int64</span></span>|  
|<span data-ttu-id="2f613-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2f613-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="2f613-165">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-165">Int64</span></span>|  
|<span data-ttu-id="2f613-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="2f613-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="2f613-167">Int32</span><span class="sxs-lookup"><span data-stu-id="2f613-167">Int32</span></span>|  
|<span data-ttu-id="2f613-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="2f613-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="2f613-169">Int16</span><span class="sxs-lookup"><span data-stu-id="2f613-169">Int16</span></span>|  
|<span data-ttu-id="2f613-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="2f613-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="2f613-171">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-171">Int64</span></span>|  
|<span data-ttu-id="2f613-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2f613-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="2f613-173">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-173">String</span></span>|  
|<span data-ttu-id="2f613-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2f613-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="2f613-175">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-175">String</span></span>|  
|<span data-ttu-id="2f613-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="2f613-177">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-177">String</span></span>|  
|<span data-ttu-id="2f613-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2f613-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="2f613-179">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-179">String</span></span>|  
|<span data-ttu-id="2f613-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2f613-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="2f613-181">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-181">String</span></span>|  
|<span data-ttu-id="2f613-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-182">COLLATION_NAME</span></span>|<span data-ttu-id="2f613-183">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-183">String</span></span>|  
|<span data-ttu-id="2f613-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2f613-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="2f613-185">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-185">String</span></span>|  
|<span data-ttu-id="2f613-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2f613-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="2f613-187">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-187">String</span></span>|  
|<span data-ttu-id="2f613-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-188">DOMAIN_NAME</span></span>|<span data-ttu-id="2f613-189">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-189">String</span></span>|  
|<span data-ttu-id="2f613-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2f613-190">DESCRIPTION</span></span>|<span data-ttu-id="2f613-191">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-191">String</span></span>|  
|<span data-ttu-id="2f613-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="2f613-192">COLUMN_LCID</span></span>|<span data-ttu-id="2f613-193">Int32</span><span class="sxs-lookup"><span data-stu-id="2f613-193">Int32</span></span>|  
|<span data-ttu-id="2f613-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="2f613-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="2f613-195">Int32</span><span class="sxs-lookup"><span data-stu-id="2f613-195">Int32</span></span>|  
|<span data-ttu-id="2f613-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="2f613-196">COLUMN_SORTID</span></span>|<span data-ttu-id="2f613-197">Int32</span><span class="sxs-lookup"><span data-stu-id="2f613-197">Int32</span></span>|  
|<span data-ttu-id="2f613-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="2f613-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="2f613-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="2f613-199">Byte[]</span></span>|  
|<span data-ttu-id="2f613-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="2f613-200">IS_COMPUTED</span></span>|<span data-ttu-id="2f613-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="2f613-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="2f613-202">Verfahren</span><span class="sxs-lookup"><span data-stu-id="2f613-202">Procedures</span></span>  
  
|<span data-ttu-id="2f613-203">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="2f613-203">ColumnName</span></span>|<span data-ttu-id="2f613-204">DataType</span><span class="sxs-lookup"><span data-stu-id="2f613-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2f613-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2f613-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="2f613-206">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-206">String</span></span>|  
|<span data-ttu-id="2f613-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2f613-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="2f613-208">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-208">String</span></span>|  
|<span data-ttu-id="2f613-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="2f613-210">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-210">String</span></span>|  
|<span data-ttu-id="2f613-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2f613-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="2f613-212">Int16</span><span class="sxs-lookup"><span data-stu-id="2f613-212">Int16</span></span>|  
|<span data-ttu-id="2f613-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="2f613-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="2f613-214">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-214">String</span></span>|  
|<span data-ttu-id="2f613-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2f613-215">DESCRIPTION</span></span>|<span data-ttu-id="2f613-216">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-216">String</span></span>|  
|<span data-ttu-id="2f613-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="2f613-217">DATE_CREATED</span></span>|<span data-ttu-id="2f613-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="2f613-218">DateTime</span></span>|  
|<span data-ttu-id="2f613-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="2f613-219">DATE_MODIFIED</span></span>|<span data-ttu-id="2f613-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="2f613-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="2f613-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="2f613-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="2f613-222">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="2f613-222">ColumnName</span></span>|<span data-ttu-id="2f613-223">DataType</span><span class="sxs-lookup"><span data-stu-id="2f613-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2f613-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2f613-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="2f613-225">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-225">String</span></span>|  
|<span data-ttu-id="2f613-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2f613-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="2f613-227">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-227">String</span></span>|  
|<span data-ttu-id="2f613-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="2f613-229">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-229">String</span></span>|  
|<span data-ttu-id="2f613-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-230">PARAMETER_NAME</span></span>|<span data-ttu-id="2f613-231">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-231">String</span></span>|  
|<span data-ttu-id="2f613-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2f613-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="2f613-233">Int32</span><span class="sxs-lookup"><span data-stu-id="2f613-233">Int32</span></span>|  
|<span data-ttu-id="2f613-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="2f613-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="2f613-235">Int32</span><span class="sxs-lookup"><span data-stu-id="2f613-235">Int32</span></span>|  
|<span data-ttu-id="2f613-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="2f613-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="2f613-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="2f613-237">Boolean</span></span>|  
|<span data-ttu-id="2f613-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="2f613-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="2f613-239">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-239">String</span></span>|  
|<span data-ttu-id="2f613-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2f613-240">IS_NULLABLE</span></span>|<span data-ttu-id="2f613-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="2f613-241">Boolean</span></span>|  
|<span data-ttu-id="2f613-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2f613-242">DATA_TYPE</span></span>|<span data-ttu-id="2f613-243">Int32</span><span class="sxs-lookup"><span data-stu-id="2f613-243">Int32</span></span>|  
|<span data-ttu-id="2f613-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2f613-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="2f613-245">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-245">Int64</span></span>|  
|<span data-ttu-id="2f613-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2f613-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="2f613-247">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-247">Int64</span></span>|  
|<span data-ttu-id="2f613-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="2f613-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="2f613-249">Int32</span><span class="sxs-lookup"><span data-stu-id="2f613-249">Int32</span></span>|  
|<span data-ttu-id="2f613-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="2f613-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="2f613-251">Int16</span><span class="sxs-lookup"><span data-stu-id="2f613-251">Int16</span></span>|  
|<span data-ttu-id="2f613-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2f613-252">DESCRIPTION</span></span>|<span data-ttu-id="2f613-253">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-253">String</span></span>|  
|<span data-ttu-id="2f613-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-254">TYPE_NAME</span></span>|<span data-ttu-id="2f613-255">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-255">String</span></span>|  
|<span data-ttu-id="2f613-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="2f613-257">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="2f613-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="2f613-258">Catalog</span></span>  
  
|<span data-ttu-id="2f613-259">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="2f613-259">ColumnName</span></span>|<span data-ttu-id="2f613-260">DataType</span><span class="sxs-lookup"><span data-stu-id="2f613-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2f613-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-261">CATALOG_NAME</span></span>|<span data-ttu-id="2f613-262">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-262">String</span></span>|  
|<span data-ttu-id="2f613-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2f613-263">DESCRIPTION</span></span>|<span data-ttu-id="2f613-264">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="2f613-265">Indexes</span><span class="sxs-lookup"><span data-stu-id="2f613-265">Indexes</span></span>  
  
|<span data-ttu-id="2f613-266">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="2f613-266">ColumnName</span></span>|<span data-ttu-id="2f613-267">DataType</span><span class="sxs-lookup"><span data-stu-id="2f613-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2f613-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2f613-268">TABLE_CATALOG</span></span>|<span data-ttu-id="2f613-269">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-269">String</span></span>|  
|<span data-ttu-id="2f613-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2f613-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="2f613-271">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-271">String</span></span>|  
|<span data-ttu-id="2f613-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-272">TABLE_NAME</span></span>|<span data-ttu-id="2f613-273">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-273">String</span></span>|  
|<span data-ttu-id="2f613-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2f613-274">INDEX_CATALOG</span></span>|<span data-ttu-id="2f613-275">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-275">String</span></span>|  
|<span data-ttu-id="2f613-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2f613-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="2f613-277">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-277">String</span></span>|  
|<span data-ttu-id="2f613-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-278">INDEX_NAME</span></span>|<span data-ttu-id="2f613-279">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-279">String</span></span>|  
|<span data-ttu-id="2f613-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="2f613-280">PRIMARY_KEY</span></span>|<span data-ttu-id="2f613-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="2f613-281">Boolean</span></span>|  
|<span data-ttu-id="2f613-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="2f613-282">UNIQUE</span></span>|<span data-ttu-id="2f613-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="2f613-283">Boolean</span></span>|  
|<span data-ttu-id="2f613-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="2f613-284">CLUSTERED</span></span>|<span data-ttu-id="2f613-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="2f613-285">Boolean</span></span>|  
|<span data-ttu-id="2f613-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="2f613-286">TYPE</span></span>|<span data-ttu-id="2f613-287">Int32</span><span class="sxs-lookup"><span data-stu-id="2f613-287">Int32</span></span>|  
|<span data-ttu-id="2f613-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="2f613-288">FILL_FACTOR</span></span>|<span data-ttu-id="2f613-289">Int32</span><span class="sxs-lookup"><span data-stu-id="2f613-289">Int32</span></span>|  
|<span data-ttu-id="2f613-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="2f613-290">INITIAL_SIZE</span></span>|<span data-ttu-id="2f613-291">Int32</span><span class="sxs-lookup"><span data-stu-id="2f613-291">Int32</span></span>|  
|<span data-ttu-id="2f613-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="2f613-292">NULLS</span></span>|<span data-ttu-id="2f613-293">Int32</span><span class="sxs-lookup"><span data-stu-id="2f613-293">Int32</span></span>|  
|<span data-ttu-id="2f613-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="2f613-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="2f613-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="2f613-295">Boolean</span></span>|  
|<span data-ttu-id="2f613-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="2f613-296">AUTO_UPDATE</span></span>|<span data-ttu-id="2f613-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="2f613-297">Boolean</span></span>|  
|<span data-ttu-id="2f613-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="2f613-298">NULL_COLLATION</span></span>|<span data-ttu-id="2f613-299">Int32</span><span class="sxs-lookup"><span data-stu-id="2f613-299">Int32</span></span>|  
|<span data-ttu-id="2f613-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2f613-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="2f613-301">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-301">Int64</span></span>|  
|<span data-ttu-id="2f613-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-302">COLUMN_NAME</span></span>|<span data-ttu-id="2f613-303">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-303">String</span></span>|  
|<span data-ttu-id="2f613-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="2f613-304">COLUMN_GUID</span></span>|<span data-ttu-id="2f613-305">Guid</span><span class="sxs-lookup"><span data-stu-id="2f613-305">Guid</span></span>|  
|<span data-ttu-id="2f613-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="2f613-306">COLUMN_PROPID</span></span>|<span data-ttu-id="2f613-307">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-307">Int64</span></span>|  
|<span data-ttu-id="2f613-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="2f613-308">COLLATION</span></span>|<span data-ttu-id="2f613-309">Int16</span><span class="sxs-lookup"><span data-stu-id="2f613-309">Int16</span></span>|  
|<span data-ttu-id="2f613-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="2f613-310">CARDINALITY</span></span>|<span data-ttu-id="2f613-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="2f613-311">Decimal</span></span>|  
|<span data-ttu-id="2f613-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="2f613-312">PAGES</span></span>|<span data-ttu-id="2f613-313">Int32</span><span class="sxs-lookup"><span data-stu-id="2f613-313">Int32</span></span>|  
|<span data-ttu-id="2f613-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="2f613-314">FILTER_CONDITION</span></span>|<span data-ttu-id="2f613-315">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-315">String</span></span>|  
|<span data-ttu-id="2f613-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="2f613-316">INTEGRATED</span></span>|<span data-ttu-id="2f613-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="2f613-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="2f613-318">Microsoft Oracle-OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="2f613-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="2f613-319">Der Microsoft Oracle OLE DB-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="2f613-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="2f613-320">Tabellen</span><span class="sxs-lookup"><span data-stu-id="2f613-320">Tables</span></span>  
  
-   <span data-ttu-id="2f613-321">Columns</span><span class="sxs-lookup"><span data-stu-id="2f613-321">Columns</span></span>  
  
-   <span data-ttu-id="2f613-322">Verfahren</span><span class="sxs-lookup"><span data-stu-id="2f613-322">Procedures</span></span>  
  
-   <span data-ttu-id="2f613-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="2f613-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="2f613-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="2f613-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="2f613-325">Ansichten</span><span class="sxs-lookup"><span data-stu-id="2f613-325">Views</span></span>  
  
-   <span data-ttu-id="2f613-326">Indexes</span><span class="sxs-lookup"><span data-stu-id="2f613-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="2f613-327">Tabellen</span><span class="sxs-lookup"><span data-stu-id="2f613-327">Tables</span></span>  
  
|<span data-ttu-id="2f613-328">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="2f613-328">ColumnName</span></span>|<span data-ttu-id="2f613-329">DataType</span><span class="sxs-lookup"><span data-stu-id="2f613-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2f613-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2f613-330">TABLE_CATALOG</span></span>|<span data-ttu-id="2f613-331">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-331">String</span></span>|  
|<span data-ttu-id="2f613-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2f613-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="2f613-333">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-333">String</span></span>|  
|<span data-ttu-id="2f613-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-334">TABLE_NAME</span></span>|<span data-ttu-id="2f613-335">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-335">String</span></span>|  
|<span data-ttu-id="2f613-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2f613-336">TABLE_TYPE</span></span>|<span data-ttu-id="2f613-337">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-337">String</span></span>|  
|<span data-ttu-id="2f613-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="2f613-338">TABLE_GUID</span></span>|<span data-ttu-id="2f613-339">Guid</span><span class="sxs-lookup"><span data-stu-id="2f613-339">Guid</span></span>|  
|<span data-ttu-id="2f613-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2f613-340">DESCRIPTION</span></span>|<span data-ttu-id="2f613-341">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-341">String</span></span>|  
|<span data-ttu-id="2f613-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="2f613-342">TABLE_PROPID</span></span>|<span data-ttu-id="2f613-343">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-343">Int64</span></span>|  
|<span data-ttu-id="2f613-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="2f613-344">DATE_CREATED</span></span>|<span data-ttu-id="2f613-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="2f613-345">DateTime</span></span>|  
|<span data-ttu-id="2f613-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="2f613-346">DATE_MODIFIED</span></span>|<span data-ttu-id="2f613-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="2f613-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="2f613-348">Columns</span><span class="sxs-lookup"><span data-stu-id="2f613-348">Columns</span></span>  
  
|<span data-ttu-id="2f613-349">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="2f613-349">ColumnName</span></span>|<span data-ttu-id="2f613-350">DataType</span><span class="sxs-lookup"><span data-stu-id="2f613-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2f613-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2f613-351">TABLE_CATALOG</span></span>|<span data-ttu-id="2f613-352">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-352">String</span></span>|  
|<span data-ttu-id="2f613-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2f613-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="2f613-354">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-354">String</span></span>|  
|<span data-ttu-id="2f613-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-355">TABLE_NAME</span></span>|<span data-ttu-id="2f613-356">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-356">String</span></span>|  
|<span data-ttu-id="2f613-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-357">COLUMN_NAME</span></span>|<span data-ttu-id="2f613-358">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-358">String</span></span>|  
|<span data-ttu-id="2f613-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="2f613-359">COLUMN_GUID</span></span>|<span data-ttu-id="2f613-360">Guid</span><span class="sxs-lookup"><span data-stu-id="2f613-360">Guid</span></span>|  
|<span data-ttu-id="2f613-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="2f613-361">COLUMN_PROPID</span></span>|<span data-ttu-id="2f613-362">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-362">Int64</span></span>|  
|<span data-ttu-id="2f613-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2f613-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="2f613-364">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-364">Int64</span></span>|  
|<span data-ttu-id="2f613-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="2f613-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="2f613-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="2f613-366">Boolean</span></span>|  
|<span data-ttu-id="2f613-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="2f613-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="2f613-368">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-368">String</span></span>|  
|<span data-ttu-id="2f613-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="2f613-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="2f613-370">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-370">Int64</span></span>|  
|<span data-ttu-id="2f613-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2f613-371">IS_NULLABLE</span></span>|<span data-ttu-id="2f613-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="2f613-372">Boolean</span></span>|  
|<span data-ttu-id="2f613-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2f613-373">DATA_TYPE</span></span>|<span data-ttu-id="2f613-374">Int32</span><span class="sxs-lookup"><span data-stu-id="2f613-374">Int32</span></span>|  
|<span data-ttu-id="2f613-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="2f613-375">TYPE_GUID</span></span>|<span data-ttu-id="2f613-376">Guid</span><span class="sxs-lookup"><span data-stu-id="2f613-376">Guid</span></span>|  
|<span data-ttu-id="2f613-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2f613-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="2f613-378">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-378">Int64</span></span>|  
|<span data-ttu-id="2f613-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2f613-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="2f613-380">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-380">Int64</span></span>|  
|<span data-ttu-id="2f613-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="2f613-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="2f613-382">Int32</span><span class="sxs-lookup"><span data-stu-id="2f613-382">Int32</span></span>|  
|<span data-ttu-id="2f613-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="2f613-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="2f613-384">Int16</span><span class="sxs-lookup"><span data-stu-id="2f613-384">Int16</span></span>|  
|<span data-ttu-id="2f613-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="2f613-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="2f613-386">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-386">Int64</span></span>|  
|<span data-ttu-id="2f613-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2f613-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="2f613-388">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-388">String</span></span>|  
|<span data-ttu-id="2f613-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2f613-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="2f613-390">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-390">String</span></span>|  
|<span data-ttu-id="2f613-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="2f613-392">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-392">String</span></span>|  
|<span data-ttu-id="2f613-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2f613-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="2f613-394">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-394">String</span></span>|  
|<span data-ttu-id="2f613-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2f613-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="2f613-396">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-396">String</span></span>|  
|<span data-ttu-id="2f613-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-397">COLLATION_NAME</span></span>|<span data-ttu-id="2f613-398">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-398">String</span></span>|  
|<span data-ttu-id="2f613-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2f613-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="2f613-400">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-400">String</span></span>|  
|<span data-ttu-id="2f613-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2f613-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="2f613-402">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-402">String</span></span>|  
|<span data-ttu-id="2f613-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-403">DOMAIN_NAME</span></span>|<span data-ttu-id="2f613-404">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-404">String</span></span>|  
|<span data-ttu-id="2f613-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2f613-405">DESCRIPTION</span></span>|<span data-ttu-id="2f613-406">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="2f613-407">Verfahren</span><span class="sxs-lookup"><span data-stu-id="2f613-407">Procedures</span></span>  
  
|<span data-ttu-id="2f613-408">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="2f613-408">ColumnName</span></span>|<span data-ttu-id="2f613-409">DataType</span><span class="sxs-lookup"><span data-stu-id="2f613-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2f613-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2f613-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="2f613-411">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-411">String</span></span>|  
|<span data-ttu-id="2f613-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2f613-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="2f613-413">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-413">String</span></span>|  
|<span data-ttu-id="2f613-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="2f613-415">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-415">String</span></span>|  
|<span data-ttu-id="2f613-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2f613-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="2f613-417">Int16</span><span class="sxs-lookup"><span data-stu-id="2f613-417">Int16</span></span>|  
|<span data-ttu-id="2f613-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="2f613-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="2f613-419">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-419">String</span></span>|  
|<span data-ttu-id="2f613-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2f613-420">DESCRIPTION</span></span>|<span data-ttu-id="2f613-421">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-421">String</span></span>|  
|<span data-ttu-id="2f613-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="2f613-422">DATE_CREATED</span></span>|<span data-ttu-id="2f613-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="2f613-423">DateTime</span></span>|  
|<span data-ttu-id="2f613-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="2f613-424">DATE_MODIFIED</span></span>|<span data-ttu-id="2f613-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="2f613-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="2f613-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="2f613-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="2f613-427">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="2f613-427">ColumnName</span></span>|<span data-ttu-id="2f613-428">DataType</span><span class="sxs-lookup"><span data-stu-id="2f613-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2f613-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2f613-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="2f613-430">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-430">String</span></span>|  
|<span data-ttu-id="2f613-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2f613-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="2f613-432">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-432">String</span></span>|  
|<span data-ttu-id="2f613-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="2f613-434">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-434">String</span></span>|  
|<span data-ttu-id="2f613-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-435">COLUMN_NAME</span></span>|<span data-ttu-id="2f613-436">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-436">String</span></span>|  
|<span data-ttu-id="2f613-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="2f613-437">COLUMN_GUID</span></span>|<span data-ttu-id="2f613-438">Guid</span><span class="sxs-lookup"><span data-stu-id="2f613-438">Guid</span></span>|  
|<span data-ttu-id="2f613-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="2f613-439">COLUMN_PROPID</span></span>|<span data-ttu-id="2f613-440">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-440">Int64</span></span>|  
|<span data-ttu-id="2f613-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="2f613-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="2f613-442">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-442">Int64</span></span>|  
|<span data-ttu-id="2f613-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2f613-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="2f613-444">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-444">Int64</span></span>|  
|<span data-ttu-id="2f613-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2f613-445">IS_NULLABLE</span></span>|<span data-ttu-id="2f613-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="2f613-446">Boolean</span></span>|  
|<span data-ttu-id="2f613-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2f613-447">DATA_TYPE</span></span>|<span data-ttu-id="2f613-448">Int32</span><span class="sxs-lookup"><span data-stu-id="2f613-448">Int32</span></span>|  
|<span data-ttu-id="2f613-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="2f613-449">TYPE_GUID</span></span>|<span data-ttu-id="2f613-450">Guid</span><span class="sxs-lookup"><span data-stu-id="2f613-450">Guid</span></span>|  
|<span data-ttu-id="2f613-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2f613-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="2f613-452">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-452">Int64</span></span>|  
|<span data-ttu-id="2f613-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2f613-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="2f613-454">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-454">Int64</span></span>|  
|<span data-ttu-id="2f613-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="2f613-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="2f613-456">Int32</span><span class="sxs-lookup"><span data-stu-id="2f613-456">Int32</span></span>|  
|<span data-ttu-id="2f613-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="2f613-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="2f613-458">Int16</span><span class="sxs-lookup"><span data-stu-id="2f613-458">Int16</span></span>|  
|<span data-ttu-id="2f613-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2f613-459">DESCRIPTION</span></span>|<span data-ttu-id="2f613-460">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-460">String</span></span>|  
|<span data-ttu-id="2f613-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="2f613-461">OVERLOAD</span></span>|<span data-ttu-id="2f613-462">Int16</span><span class="sxs-lookup"><span data-stu-id="2f613-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="2f613-463">Ansichten</span><span class="sxs-lookup"><span data-stu-id="2f613-463">Views</span></span>  
  
|<span data-ttu-id="2f613-464">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="2f613-464">ColumnName</span></span>|<span data-ttu-id="2f613-465">DataType</span><span class="sxs-lookup"><span data-stu-id="2f613-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2f613-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2f613-466">TABLE_CATALOG</span></span>|<span data-ttu-id="2f613-467">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-467">String</span></span>|  
|<span data-ttu-id="2f613-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2f613-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="2f613-469">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-469">String</span></span>|  
|<span data-ttu-id="2f613-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-470">TABLE_NAME</span></span>|<span data-ttu-id="2f613-471">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-471">String</span></span>|  
|<span data-ttu-id="2f613-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="2f613-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="2f613-473">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-473">String</span></span>|  
|<span data-ttu-id="2f613-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="2f613-474">CHECK_OPTION</span></span>|<span data-ttu-id="2f613-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="2f613-475">Boolean</span></span>|  
|<span data-ttu-id="2f613-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="2f613-476">IS_UPDATABLE</span></span>|<span data-ttu-id="2f613-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="2f613-477">Boolean</span></span>|  
|<span data-ttu-id="2f613-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2f613-478">DESCRIPTION</span></span>|<span data-ttu-id="2f613-479">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-479">String</span></span>|  
|<span data-ttu-id="2f613-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="2f613-480">DATE_CREATED</span></span>|<span data-ttu-id="2f613-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="2f613-481">DateTime</span></span>|  
|<span data-ttu-id="2f613-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="2f613-482">DATE_MODIFIED</span></span>|<span data-ttu-id="2f613-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="2f613-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="2f613-484">Indexes</span><span class="sxs-lookup"><span data-stu-id="2f613-484">Indexes</span></span>  
  
|<span data-ttu-id="2f613-485">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="2f613-485">ColumnName</span></span>|<span data-ttu-id="2f613-486">DataType</span><span class="sxs-lookup"><span data-stu-id="2f613-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2f613-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2f613-487">TABLE_CATALOG</span></span>|<span data-ttu-id="2f613-488">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-488">String</span></span>|  
|<span data-ttu-id="2f613-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2f613-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="2f613-490">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-490">String</span></span>|  
|<span data-ttu-id="2f613-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-491">TABLE_NAME</span></span>|<span data-ttu-id="2f613-492">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-492">String</span></span>|  
|<span data-ttu-id="2f613-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2f613-493">INDEX_CATALOG</span></span>|<span data-ttu-id="2f613-494">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-494">String</span></span>|  
|<span data-ttu-id="2f613-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2f613-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="2f613-496">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-496">String</span></span>|  
|<span data-ttu-id="2f613-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-497">INDEX_NAME</span></span>|<span data-ttu-id="2f613-498">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-498">String</span></span>|  
|<span data-ttu-id="2f613-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="2f613-499">PRIMARY_KEY</span></span>|<span data-ttu-id="2f613-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="2f613-500">Boolean</span></span>|  
|<span data-ttu-id="2f613-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="2f613-501">UNIQUE</span></span>|<span data-ttu-id="2f613-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="2f613-502">Boolean</span></span>|  
|<span data-ttu-id="2f613-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="2f613-503">CLUSTERED</span></span>|<span data-ttu-id="2f613-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="2f613-504">Boolean</span></span>|  
|<span data-ttu-id="2f613-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="2f613-505">TYPE</span></span>|<span data-ttu-id="2f613-506">Int32</span><span class="sxs-lookup"><span data-stu-id="2f613-506">Int32</span></span>|  
|<span data-ttu-id="2f613-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="2f613-507">FILL_FACTOR</span></span>|<span data-ttu-id="2f613-508">Int32</span><span class="sxs-lookup"><span data-stu-id="2f613-508">Int32</span></span>|  
|<span data-ttu-id="2f613-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="2f613-509">INITIAL_SIZE</span></span>|<span data-ttu-id="2f613-510">Int32</span><span class="sxs-lookup"><span data-stu-id="2f613-510">Int32</span></span>|  
|<span data-ttu-id="2f613-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="2f613-511">NULLS</span></span>|<span data-ttu-id="2f613-512">Int32</span><span class="sxs-lookup"><span data-stu-id="2f613-512">Int32</span></span>|  
|<span data-ttu-id="2f613-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="2f613-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="2f613-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="2f613-514">Boolean</span></span>|  
|<span data-ttu-id="2f613-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="2f613-515">AUTO_UPDATE</span></span>|<span data-ttu-id="2f613-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="2f613-516">Boolean</span></span>|  
|<span data-ttu-id="2f613-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="2f613-517">NULL_COLLATION</span></span>|<span data-ttu-id="2f613-518">Int32</span><span class="sxs-lookup"><span data-stu-id="2f613-518">Int32</span></span>|  
|<span data-ttu-id="2f613-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2f613-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="2f613-520">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-520">Int64</span></span>|  
|<span data-ttu-id="2f613-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-521">COLUMN_NAME</span></span>|<span data-ttu-id="2f613-522">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-522">String</span></span>|  
|<span data-ttu-id="2f613-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="2f613-523">COLUMN_GUID</span></span>|<span data-ttu-id="2f613-524">Guid</span><span class="sxs-lookup"><span data-stu-id="2f613-524">Guid</span></span>|  
|<span data-ttu-id="2f613-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="2f613-525">COLUMN_PROPID</span></span>|<span data-ttu-id="2f613-526">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-526">Int64</span></span>|  
|<span data-ttu-id="2f613-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="2f613-527">COLLATION</span></span>|<span data-ttu-id="2f613-528">Int16</span><span class="sxs-lookup"><span data-stu-id="2f613-528">Int16</span></span>|  
|<span data-ttu-id="2f613-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="2f613-529">CARDINALITY</span></span>|<span data-ttu-id="2f613-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="2f613-530">Decimal</span></span>|  
|<span data-ttu-id="2f613-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="2f613-531">PAGES</span></span>|<span data-ttu-id="2f613-532">Int32</span><span class="sxs-lookup"><span data-stu-id="2f613-532">Int32</span></span>|  
|<span data-ttu-id="2f613-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="2f613-533">FILTER_CONDITION</span></span>|<span data-ttu-id="2f613-534">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-534">String</span></span>|  
|<span data-ttu-id="2f613-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="2f613-535">INTEGRATED</span></span>|<span data-ttu-id="2f613-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="2f613-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="2f613-537">Microsoft Jet OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="2f613-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="2f613-538">Der Microsoft Jet OLE DB-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="2f613-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="2f613-539">Tabellen</span><span class="sxs-lookup"><span data-stu-id="2f613-539">Tables</span></span>  
  
-   <span data-ttu-id="2f613-540">Columns</span><span class="sxs-lookup"><span data-stu-id="2f613-540">Columns</span></span>  
  
-   <span data-ttu-id="2f613-541">Verfahren</span><span class="sxs-lookup"><span data-stu-id="2f613-541">Procedures</span></span>  
  
-   <span data-ttu-id="2f613-542">Ansichten</span><span class="sxs-lookup"><span data-stu-id="2f613-542">Views</span></span>  
  
-   <span data-ttu-id="2f613-543">Indexes</span><span class="sxs-lookup"><span data-stu-id="2f613-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="2f613-544">Tabellen</span><span class="sxs-lookup"><span data-stu-id="2f613-544">Tables</span></span>  
  
|<span data-ttu-id="2f613-545">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="2f613-545">ColumnName</span></span>|<span data-ttu-id="2f613-546">DataType</span><span class="sxs-lookup"><span data-stu-id="2f613-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2f613-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2f613-547">TABLE_CATALOG</span></span>|<span data-ttu-id="2f613-548">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-548">String</span></span>|  
|<span data-ttu-id="2f613-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2f613-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="2f613-550">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-550">String</span></span>|  
|<span data-ttu-id="2f613-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-551">TABLE_NAME</span></span>|<span data-ttu-id="2f613-552">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-552">String</span></span>|  
|<span data-ttu-id="2f613-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2f613-553">TABLE_TYPE</span></span>|<span data-ttu-id="2f613-554">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-554">String</span></span>|  
|<span data-ttu-id="2f613-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="2f613-555">TABLE_GUID</span></span>|<span data-ttu-id="2f613-556">Guid</span><span class="sxs-lookup"><span data-stu-id="2f613-556">Guid</span></span>|  
|<span data-ttu-id="2f613-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2f613-557">DESCRIPTION</span></span>|<span data-ttu-id="2f613-558">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-558">String</span></span>|  
|<span data-ttu-id="2f613-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="2f613-559">TABLE_PROPID</span></span>|<span data-ttu-id="2f613-560">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-560">Int64</span></span>|  
|<span data-ttu-id="2f613-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="2f613-561">DATE_CREATED</span></span>|<span data-ttu-id="2f613-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="2f613-562">DateTime</span></span>|  
|<span data-ttu-id="2f613-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="2f613-563">DATE_MODIFIED</span></span>|<span data-ttu-id="2f613-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="2f613-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="2f613-565">Columns</span><span class="sxs-lookup"><span data-stu-id="2f613-565">Columns</span></span>  
  
|<span data-ttu-id="2f613-566">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="2f613-566">ColumnName</span></span>|<span data-ttu-id="2f613-567">DataType</span><span class="sxs-lookup"><span data-stu-id="2f613-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2f613-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2f613-568">TABLE_CATALOG</span></span>|<span data-ttu-id="2f613-569">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-569">String</span></span>|  
|<span data-ttu-id="2f613-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2f613-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="2f613-571">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-571">String</span></span>|  
|<span data-ttu-id="2f613-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-572">TABLE_NAME</span></span>|<span data-ttu-id="2f613-573">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-573">String</span></span>|  
|<span data-ttu-id="2f613-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-574">COLUMN_NAME</span></span>|<span data-ttu-id="2f613-575">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-575">String</span></span>|  
|<span data-ttu-id="2f613-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="2f613-576">COLUMN_GUID</span></span>|<span data-ttu-id="2f613-577">Guid</span><span class="sxs-lookup"><span data-stu-id="2f613-577">Guid</span></span>|  
|<span data-ttu-id="2f613-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="2f613-578">COLUMN_PROPID</span></span>|<span data-ttu-id="2f613-579">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-579">Int64</span></span>|  
|<span data-ttu-id="2f613-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2f613-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="2f613-581">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-581">Int64</span></span>|  
|<span data-ttu-id="2f613-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="2f613-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="2f613-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="2f613-583">Boolean</span></span>|  
|<span data-ttu-id="2f613-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="2f613-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="2f613-585">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-585">String</span></span>|  
|<span data-ttu-id="2f613-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="2f613-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="2f613-587">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-587">Int64</span></span>|  
|<span data-ttu-id="2f613-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2f613-588">IS_NULLABLE</span></span>|<span data-ttu-id="2f613-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="2f613-589">Boolean</span></span>|  
|<span data-ttu-id="2f613-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2f613-590">DATA_TYPE</span></span>|<span data-ttu-id="2f613-591">Int32</span><span class="sxs-lookup"><span data-stu-id="2f613-591">Int32</span></span>|  
|<span data-ttu-id="2f613-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="2f613-592">TYPE_GUID</span></span>|<span data-ttu-id="2f613-593">Guid</span><span class="sxs-lookup"><span data-stu-id="2f613-593">Guid</span></span>|  
|<span data-ttu-id="2f613-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2f613-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="2f613-595">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-595">Int64</span></span>|  
|<span data-ttu-id="2f613-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2f613-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="2f613-597">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-597">Int64</span></span>|  
|<span data-ttu-id="2f613-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="2f613-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="2f613-599">Int32</span><span class="sxs-lookup"><span data-stu-id="2f613-599">Int32</span></span>|  
|<span data-ttu-id="2f613-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="2f613-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="2f613-601">Int16</span><span class="sxs-lookup"><span data-stu-id="2f613-601">Int16</span></span>|  
|<span data-ttu-id="2f613-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="2f613-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="2f613-603">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-603">Int64</span></span>|  
|<span data-ttu-id="2f613-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2f613-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="2f613-605">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-605">String</span></span>|  
|<span data-ttu-id="2f613-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2f613-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="2f613-607">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-607">String</span></span>|  
|<span data-ttu-id="2f613-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="2f613-609">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-609">String</span></span>|  
|<span data-ttu-id="2f613-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2f613-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="2f613-611">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-611">String</span></span>|  
|<span data-ttu-id="2f613-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2f613-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="2f613-613">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-613">String</span></span>|  
|<span data-ttu-id="2f613-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-614">COLLATION_NAME</span></span>|<span data-ttu-id="2f613-615">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-615">String</span></span>|  
|<span data-ttu-id="2f613-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2f613-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="2f613-617">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-617">String</span></span>|  
|<span data-ttu-id="2f613-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2f613-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="2f613-619">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-619">String</span></span>|  
|<span data-ttu-id="2f613-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-620">DOMAIN_NAME</span></span>|<span data-ttu-id="2f613-621">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-621">String</span></span>|  
|<span data-ttu-id="2f613-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2f613-622">DESCRIPTION</span></span>|<span data-ttu-id="2f613-623">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="2f613-624">Verfahren</span><span class="sxs-lookup"><span data-stu-id="2f613-624">Procedures</span></span>  
  
|<span data-ttu-id="2f613-625">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="2f613-625">ColumnName</span></span>|<span data-ttu-id="2f613-626">DataType</span><span class="sxs-lookup"><span data-stu-id="2f613-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2f613-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2f613-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="2f613-628">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-628">String</span></span>|  
|<span data-ttu-id="2f613-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2f613-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="2f613-630">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-630">String</span></span>|  
|<span data-ttu-id="2f613-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="2f613-632">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-632">String</span></span>|  
|<span data-ttu-id="2f613-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2f613-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="2f613-634">Int16</span><span class="sxs-lookup"><span data-stu-id="2f613-634">Int16</span></span>|  
|<span data-ttu-id="2f613-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="2f613-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="2f613-636">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-636">String</span></span>|  
|<span data-ttu-id="2f613-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2f613-637">DESCRIPTION</span></span>|<span data-ttu-id="2f613-638">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-638">String</span></span>|  
|<span data-ttu-id="2f613-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="2f613-639">DATE_CREATED</span></span>|<span data-ttu-id="2f613-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="2f613-640">DateTime</span></span>|  
|<span data-ttu-id="2f613-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="2f613-641">DATE_MODIFIED</span></span>|<span data-ttu-id="2f613-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="2f613-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="2f613-643">Ansichten</span><span class="sxs-lookup"><span data-stu-id="2f613-643">Views</span></span>  
  
|<span data-ttu-id="2f613-644">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="2f613-644">ColumnName</span></span>|<span data-ttu-id="2f613-645">DataType</span><span class="sxs-lookup"><span data-stu-id="2f613-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2f613-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2f613-646">TABLE_CATALOG</span></span>|<span data-ttu-id="2f613-647">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-647">String</span></span>|  
|<span data-ttu-id="2f613-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2f613-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="2f613-649">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-649">String</span></span>|  
|<span data-ttu-id="2f613-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-650">TABLE_NAME</span></span>|<span data-ttu-id="2f613-651">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-651">String</span></span>|  
|<span data-ttu-id="2f613-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="2f613-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="2f613-653">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-653">String</span></span>|  
|<span data-ttu-id="2f613-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="2f613-654">CHECK_OPTION</span></span>|<span data-ttu-id="2f613-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="2f613-655">Boolean</span></span>|  
|<span data-ttu-id="2f613-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="2f613-656">IS_UPDATABLE</span></span>|<span data-ttu-id="2f613-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="2f613-657">Boolean</span></span>|  
|<span data-ttu-id="2f613-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2f613-658">DESCRIPTION</span></span>|<span data-ttu-id="2f613-659">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-659">String</span></span>|  
|<span data-ttu-id="2f613-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="2f613-660">DATE_CREATED</span></span>|<span data-ttu-id="2f613-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="2f613-661">DateTime</span></span>|  
|<span data-ttu-id="2f613-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="2f613-662">DATE_MODIFIED</span></span>|<span data-ttu-id="2f613-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="2f613-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="2f613-664">Indexes</span><span class="sxs-lookup"><span data-stu-id="2f613-664">Indexes</span></span>  
  
|<span data-ttu-id="2f613-665">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="2f613-665">ColumnName</span></span>|<span data-ttu-id="2f613-666">DataType</span><span class="sxs-lookup"><span data-stu-id="2f613-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2f613-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2f613-667">TABLE_CATALOG</span></span>|<span data-ttu-id="2f613-668">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-668">String</span></span>|  
|<span data-ttu-id="2f613-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2f613-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="2f613-670">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-670">String</span></span>|  
|<span data-ttu-id="2f613-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-671">TABLE_NAME</span></span>|<span data-ttu-id="2f613-672">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-672">String</span></span>|  
|<span data-ttu-id="2f613-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2f613-673">INDEX_CATALOG</span></span>|<span data-ttu-id="2f613-674">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-674">String</span></span>|  
|<span data-ttu-id="2f613-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2f613-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="2f613-676">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-676">String</span></span>|  
|<span data-ttu-id="2f613-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-677">INDEX_NAME</span></span>|<span data-ttu-id="2f613-678">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-678">String</span></span>|  
|<span data-ttu-id="2f613-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="2f613-679">PRIMARY_KEY</span></span>|<span data-ttu-id="2f613-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="2f613-680">Boolean</span></span>|  
|<span data-ttu-id="2f613-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="2f613-681">UNIQUE</span></span>|<span data-ttu-id="2f613-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="2f613-682">Boolean</span></span>|  
|<span data-ttu-id="2f613-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="2f613-683">CLUSTERED</span></span>|<span data-ttu-id="2f613-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="2f613-684">Boolean</span></span>|  
|<span data-ttu-id="2f613-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="2f613-685">TYPE</span></span>|<span data-ttu-id="2f613-686">Int32</span><span class="sxs-lookup"><span data-stu-id="2f613-686">Int32</span></span>|  
|<span data-ttu-id="2f613-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="2f613-687">FILL_FACTOR</span></span>|<span data-ttu-id="2f613-688">Int32</span><span class="sxs-lookup"><span data-stu-id="2f613-688">Int32</span></span>|  
|<span data-ttu-id="2f613-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="2f613-689">INITIAL_SIZE</span></span>|<span data-ttu-id="2f613-690">Int32</span><span class="sxs-lookup"><span data-stu-id="2f613-690">Int32</span></span>|  
|<span data-ttu-id="2f613-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="2f613-691">NULLS</span></span>|<span data-ttu-id="2f613-692">Int32</span><span class="sxs-lookup"><span data-stu-id="2f613-692">Int32</span></span>|  
|<span data-ttu-id="2f613-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="2f613-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="2f613-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="2f613-694">Boolean</span></span>|  
|<span data-ttu-id="2f613-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="2f613-695">AUTO_UPDATE</span></span>|<span data-ttu-id="2f613-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="2f613-696">Boolean</span></span>|  
|<span data-ttu-id="2f613-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="2f613-697">NULL_COLLATION</span></span>|<span data-ttu-id="2f613-698">Int32</span><span class="sxs-lookup"><span data-stu-id="2f613-698">Int32</span></span>|  
|<span data-ttu-id="2f613-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2f613-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="2f613-700">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-700">Int64</span></span>|  
|<span data-ttu-id="2f613-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2f613-701">COLUMN_NAME</span></span>|<span data-ttu-id="2f613-702">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-702">String</span></span>|  
|<span data-ttu-id="2f613-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="2f613-703">COLUMN_GUID</span></span>|<span data-ttu-id="2f613-704">Guid</span><span class="sxs-lookup"><span data-stu-id="2f613-704">Guid</span></span>|  
|<span data-ttu-id="2f613-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="2f613-705">COLUMN_PROPID</span></span>|<span data-ttu-id="2f613-706">Int64</span><span class="sxs-lookup"><span data-stu-id="2f613-706">Int64</span></span>|  
|<span data-ttu-id="2f613-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="2f613-707">COLLATION</span></span>|<span data-ttu-id="2f613-708">Int16</span><span class="sxs-lookup"><span data-stu-id="2f613-708">Int16</span></span>|  
|<span data-ttu-id="2f613-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="2f613-709">CARDINALITY</span></span>|<span data-ttu-id="2f613-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="2f613-710">Decimal</span></span>|  
|<span data-ttu-id="2f613-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="2f613-711">PAGES</span></span>|<span data-ttu-id="2f613-712">Int32</span><span class="sxs-lookup"><span data-stu-id="2f613-712">Int32</span></span>|  
|<span data-ttu-id="2f613-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="2f613-713">FILTER_CONDITION</span></span>|<span data-ttu-id="2f613-714">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f613-714">String</span></span>|  
|<span data-ttu-id="2f613-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="2f613-715">INTEGRATED</span></span>|<span data-ttu-id="2f613-716">Boolesch</span><span class="sxs-lookup"><span data-stu-id="2f613-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2f613-717">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f613-717">See Also</span></span>  
 [<span data-ttu-id="2f613-718">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="2f613-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
