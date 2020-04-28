HOW TO FIX THE ERROR:

django.core.exceptions.ImproperlyConfigured: URL route 'delete/<list:id>/' uses invalid converter 'list'.


CHANGE YOUR urls.py in your app(notproject)

    urlpatterns = [
        ...
        path('delete/<list_id>', views.delete, name="delete"),
        ...
      ]
      
      into

    urlpatterns = [
      ...
      path('delete/<list_id>/', views.delete, name="delete"),
      ...
    ]
    
TAKE NOTE OF "/" AFTER list_id. This is due to django3 new URL dispatcher. https://docs.djangoproject.com/en/3.0/topics/http/urls/
  
You can see the whole code in todo_list/urls.py  
    
    
