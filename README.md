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
