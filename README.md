# Magento Attribute Helpers

Add or edit a comment / helper on custom or native Magento attributes.

    $this->updateAttribute('catalog_product', 'custom_att_code', 'note', 'This comment will be seen as a comment in the admin area of Magento underneath an attribute field...');

Can be applied when creating a custom attribute - just add 'note' as a parameter when creating a new attribute. Example:

    $installer = $this;
    $installer->startSetup();
    $attribute  = array(
        'type'          =>  'text',
        'label'         =>  'Custom Att Name',
        'input'         =>  'select',
        // ..... MORE PARAMETERS, etc //
        'note'          =>  'This comment will be seen as a comment in the admin area of Magento underneath an attribute field...'
    );
    $installer->addAttribute('catalog_category', 'custom_att_code', $attribute);
    $installer->endSetup();

NOTE: I have also included an upgrade script (mysql4-upgrade-0.0.1-0.0.2.php) to demonstrate how you'd update a comment / note that already exists for an attribute. For this to take effect, ensure the current version in your config.xml file is set to the latest version:

    <Samuidavid_AttributeHelpers>
        <version>0.0.2</version>
    </Samuidavid_AttributeHelpers>

Remember to refresh the cache once uploaded! The script will execute once you're in the admin area and go to a product page which has an attribute set that contains the custom attribute.

TIP: To ensure you're module is running the correct version, run the following query on your database:

    select * from core_resource;

Look for your module name (in this case, it's "attributehelpers" and make sure the version is up-to-date)...