# Test Code (Django & React)

## models.py

```
class Company(models.Model):
    name = models.CharField('Name'), max_length=300)

class Office(models.Model):
    street = models.CharField('Street', max_length=256, blank=True)
    postal_code = models.CharField('Postal Code', max_length=32, blank=True)
    city = models.CharField('City', max_length=128, blank=True, null=True)
    monthly_rent = models.DecimalField(decimal_places=2, max_digits=10, blank=True, null=True)
```

## serializers.py

```
class CompanySerializer(serializers.ModelSerializer):
```

## views.py

```
class CompanyListViewSet(ModelViewSet):
    serializer_class = CompanySerializer
```

## urls.py

```
router.register(r'companies', ContactListViewCompanyListViewSetSet, base_name='company')
```

 > -- note -- if you dunno django, then go forward with node.js with using Sequelize. But django would be preferred. 

## Requirements / Tasks

1. Please change the models so that the following functionality works. How do you test it?

 - A Company can have one or more offices
 - Offices can be an headquarter.
 - A company should at all times have exactly one headquarter

2. Please add an API with the help of django-rest-framework. How would you test the functionality?

 - Write an API endpoint to create the company along with office information
 - Write an simple read-only API endpoint for companies to get the company name + street+postal_code+city from the headquarter office
 - Write an simple read-only API endpoint to get all the offices for a company
 - Write an API endpoint to change the headquarter of the company

3. Make a simple React app to show above API usability as much as possible (no designs here, it's all up to you), but should use Redux lifecycle.

4. BONUS:

 - Customize the API endpoint to include the sum of rent for all offices of a Company. How would you approach / test this?
