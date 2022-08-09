<?php

namespace App\Http\Controllers\Site;

use App\Http\Controllers\Controller;
use App\Models\Category;
use App\Models\Service;
use App\Models\Store;
use Illuminate\Http\Request;

class CategoryController extends Controller
{
    public function stores(Request $request, $slug = null)
    {
        if (empty($slug)) {

            return redirect()->back();

        } else {

            $data = '';
            // get the category id to get all of category level and stores
            $category =  Category::where('slug', $slug)->firstOrFail();

            $category_id = $category['id'];

            $categoreyLevel = "";

            $stores = "";

            if ($slug == 'shop') {
                // retrive the shop service as category level
                // categoryLevel == services
                $categoreyLevel =  Service::all();

                $stores = null;
            }

            elseif (!empty(Store::where('category_id', $category_id))) {
                // return "done";
                // retrive dine and entertainment
                // categoryLevel == services

                // $categoreyLevel =  Service::where('category_id', $category_id)->firstOrFail();

                $stores =  Store::where('category_id', $category_id)->get();

            }



        }

        return view('site.category', compact('categoreyLevel', 'stores'));
    } // end store

} // end of controller
