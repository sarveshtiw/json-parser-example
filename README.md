# json-parser-example

var json = {
  YourReference: {
    sysid: "hgjhg",
    stepSequenceNum: '1',
    currentStepName: 'Your reference',
    id: 'yourReference_ID',
    nextStepName: 'ConfigurationItem',
    listOfFields: [
      {
        componentType: 'Accordion',
        props: {
          data: {
            displayAccordion: true,
            id: 'incidentDetailsForm',
            name: 'incidentDetailsForm',
            alwaysExpanded: true,
            header: {
              type: 'Title',
              headerData: {
                title: 'Please enter incident details'
              }
            },
            content: {
              type: 'FormContent',
              gridEnable: true,
              contentData: [
                {
                  componentType: 'TextField',
                  props: {
                    data: {
                      id: 'yourReference',
                      name: 'yourReference',
                      title: '',
                      placeholder: '',
                      value: '',
                      maxLength: 40,
                      labelField: {
                        labelname: 'Your reference',
                        isRequired: 'optional',
                        type: 'labelDefault',
                        fontSizeType: 'sm',
                        htmlFor: 'yourReference',
                        id: 'yourReference_label'
                      },
                      helpText: {
                        labelname: 'A maximum of 40 character can be entered for reference',
                        type: 'labelHelperLightSM',
                        fontSizeType: 'sm'
                      },
                      classNames: {
                        columnType: 'col-wrap column-2'
                      }
                    }
                  }
                },
                {
                  componentType: 'DropdownComponent',
                  props: {
                    data: {
                      CreateHandler: 'setCatagoryOnBusinessService|onChange',
                      id: 'businessService',
                      name: 'businessService',
                      title: 'Select business service',
                      dropdownValues: [
                        
                      ],
                      helpText: {
                        labelname: 'Please select the service on which you are raising the incident',
                        type: 'labelHelperLightSM',
                        fontSizeType: 'sm'
                      },
                      label: {
                        id: 'businessService_label',
                        htmlFor: 'businessService',
                        type: 'labelDefault',
                        labelname: 'Business service',
                        fontSizeType: 'sm'
                      },
                      classNames: {
                        columnType: 'col-wrap column-2 pull-right'
                      },
                      apiData: '@QueryList.dropdownValues.optionName.optionValue|businessServices|businessServices.name|businessServices.name'
                    }
                  }
                },
                {
                  componentType: 'DropdownComponent',
                  props: {
                    data: {
                      CreateHandler: 'setSubCategoryOnCatagory|onChange',
                      id: 'category',
                      name: 'category',
                      title: 'Select category',
                      dropdownValues: [
                        
                      ],
                      helpText: {
                        labelname: 'Please select or type the incident category to classify the incident',
                        type: 'labelHelperLightSM',
                        fontSizeType: 'sm'
                      },
                      label: {
                        id: 'category_label',
                        htmlFor: 'category',
                        type: 'labelDefault',
                        labelname: 'Category',
                        fontSizeType: 'sm'
                      },
                      classNames: {
                        columnType: 'col-wrap column-2'
                      }
                    }
                  }
                },
                {
                  componentType: 'DropdownComponent',
                  props: {
                    data: {
                      CreateHandler: 'setValueAndIdToFormData|onChange',
                      id: 'subCategory',
                      name: 'subCategory',
                      title: 'Select sub category',
                      dropdownValues: [
                        
                      ],
                      helpText: {
                        labelname: 'Please select the incident sub category to classify the incident',
                        type: 'labelHelperLightSM',
                        fontSizeType: 'sm'
                      },
                      label: {
                        id: 'subCategory_label',
                        isRequired: 'optional',
                        htmlFor: 'subCategory',
                        type: 'labelDefault',
                        labelname: 'Sub category',
                        fontSizeType: 'sm'
                      },
                      classNames: {
                        columnType: 'col-wrap column-2 pull-right'
                      }
                    }
                  }
                },
                {
                  componentType: 'Label',
                  props: {
                    data: {
                      id: 'summary_label',
                      htmlFor: 'summary',
                      type: 'labelDefault',
                      labelname: 'Summary',
                      classNames: {
                        columnType: 'col-wrap column-1 summary-txt'
                      }
                    }
                  }
                },
                {
                  componentType: 'TextArea',
                  props: {
                    data: {
                      id: 'summary',
                      name: 'summary',
                      rows: 5,
                      label: '',
                      maxLength: 160,
                      title: '',
                      placeholder: '',
                      label_header_left: {
                        labelname: '',
                        type: 'labelDefault',
                        isInline: true,
                        fontSizeType: 'lg'
                      },
                      label_header_right: {
                        labelname: 'characters left',
                        type: 'labelDefault',
                        isInline: true,
                        fontSizeType: 'lg'
                      },
                      classNames: {
                        columnType: 'col-wrap column-1 txt-area'
                      }
                    }
                  }
                }
              ]
            }
          }
        }
      }
    ],
    footerFields: [
      {
        componentType: 'Button',
        props: {
          data: {
            location: 'right',
            isIcon: true,
            id: 'nextButton',
            name: 'Configuration item',
            type: 'primary',
            buttonType: 'button',
            CreateHandler: 'incidentNextClickHandler|onClick'
          }
        },
        alignmentClass: 'pull_right',
        validateForm: true
      },
      {
        componentType: 'Button',
        props: {
          data: {
            id: 'gotoOrder',
            name: 'Back to tickets',
            type: 'tertiary',
            buttonType: 'button',
            CreateHandler: 'redirectToTickets|onClick'
          }
        },
        alignmentClass: 'pull_left',
        validateForm: false
      }
    ],
    validationRules: {
      rules: [
        {
          ruleName: 'REQUIRED',
          applicableFields: [
            'businessService',
            'category',
            'summary'
          ],
          message: 'This is mandatory field'
        }
      ],
      messageProps: {
        type: 'warning',
        name: 'warning',
        id: 'validationError',
        lightBackground: true,
        arrowRequired: true,
        messageTitle: 'Sorry, there were @count errors:',
        messageBody: ''
      }
    },
    initialAPI: [
      {
        queryName: 'BUSINESS_SERVICES',
        responseObjectName: 'businessServices'
      }
    ],
    decorators: [
      
    ]
  },
  UploadFiles: {
    stepSequenceNum: '5',
    currentStepName: 'Upload files',
    id: 'uploadFiles_ID',
    prevStepName: 'Impact',
    nextStepName: 'Summary',
    listOfFields: [
      {
        componentType: 'Accordion',
        props: {
          data: {
            alwaysExpanded: true,
            id: 'incidentDetailsForm',
            name: 'incidentDetailsForm',
            displayAccordion: true,
            header: {
              type: 'Title',
              headerData: {
                title: 'Attach files'
              }
            },
            content: {
              type: 'FormContent',
              contentData: [
                {
                  componentType: 'FileUpload',
                  props: {
                    data: {
                      label_header_left: {
                        labelname: 'Add an incident template or any additional files that will help to identify your problem',
                        type: 'labelDefault',
                        isInline: false,
                        fontSizeType: 'lg',
                        id: 'fileNames_label',
                        isRequired: 'optional',
                        htmlFor: 'fileUpl'
                      },
                      id: 'fileUpl',
                      name: 'fileUpl',
                      summaryLabel: {
                        labelname: 'Upload files',
                        htmlFor: 'fileNames'
                      },
                      upload_text: '',
                      drag_drop_text: 'Drag and drop file here to upload',
                      max_file: 'Max file size: 20MB per fill',
                      or: 'or',
                      fileDetails: {
                        
                      },
                      url: '/upload',
                      buttonConfig: {
                        id: 'tertiary',
                        name: 'Attach file(s)',
                        type: 'tertiary',
                        buttonType: 'button'
                      },
                      CreateHandler1: 'onDelete|onDelete',
                      CreateHandler2: 'handleOrderFileUploadError|hadleValidationError',
                      CreateHandler: 'onChange|onChange',
                      extensionsAllowed: '.pdf,.png,.jpeg,.jpg,.doc,.docx,.htm,.html,.xls,.xlsx,.ppt,.pptx,.vsd,.vsdx,.rtf,.txt,.bmp',
                      classNames: {
                        columnType: 'file-upload'
                      }
                    }
                  }
                },
                {
                  componentType: 'Label',
                  props: {
                    data: {
                      id: '_help',
                      htmlFor: '',
                      type: 'labelHelperLightXS',
                      classNames: {
                        columnType: 'nomargin'
                      },
                      labelname: 'You can attach these files only .pdf,.png,.jpeg,.jpg,.doc,.docx,.htm,.html,.xls,.xlsx,.ppt,.pptx,.vsd,.vsdx,.rtf,.txt,.bmp'
                    }
                  }
                }
              ]
            }
          }
        }
      }
    ],
    footerFields: [
      {
        componentType: 'Button',
        props: {
          data: {
            location: 'right',
            isIcon: true,
            id: 'nextButton',
            name: 'Summary',
            type: 'primary',
            buttonType: 'button',
            CreateHandler: 'incidentNextClickHandler|onClick'
          }
        },
        alignmentClass: 'pull_right',
        validateForm: true
      },
      {
        componentType: 'Button',
        props: {
          data: {
            id: 'backButton',
            name: 'Steps taken',
            location: 'left',
            isIcon: true,
            type: 'secondary',
            buttonType: 'button',
            CreateHandler: 'backClickHandler|onClick'
          }
        },
        alignmentClass: 'pull_right'
      },
      {
        componentType: 'Button',
        props: {
          data: {
            id: 'tickets',
            name: 'Back to tickets',
            type: 'tertiary',
            buttonType: 'button',
            CreateHandler: 'redirectToTickets|onClick'
          }
        },
        alignmentClass: 'pull_left'
      }
    ],
    validationRules: {
      rules: [
        
      ],
      messageProps: {
        type: 'warning',
        name: 'warning',
        id: 'validationError',
        lightBackground: true,
        arrowRequired: true,
        messageTitle: 'Sorry, there were @count errors',
        messageBody: ''
      }
    }
  },
  Summary: {
    stepSequenceNum: '6',
    currentStepName: 'Summary',
    isSummary: true,
    id: 'Summary_ID',
    prevStepName: 'UploadFiles',
    journey: 'RaiseIncident',
    listOfFields: [
      {
        componentType: 'AlertMessage',
        criteria: {
          leftOperand: 'MessageStatus',
          condition: 'EQUAL',
          rightOperand: 'incidentRaised'
        },
        props: {
          data: {
            type: 'info',
            name: 'info',
            id: 'd_i_wa_link',
            lightBackground: false,
            arrowRequired: true,
            messageTitle: 'Your incident ',
            messageTitleLink: '',
            messageTitle1: ' has been raised',
            CreateHandler: 'viewIncident|linkClick',
            apiData: '@FormData.messageTitleLink|generalInfo.messageTitleLink',
            messageBody: 'The files you uploaded will be available shortly.'
          }
        }
      },
      {
        componentType: 'Label',
        criteria: {
          leftOperand: 'MessageStatus',
          condition: 'NOTEQUAL',
          rightOperand: 'incidentRaised'
        },
        props: {
          data: {
            id: 'incSummary_label',
            isRequired: false,
            htmlFor: '',
            type: 'labelHeadingNBCenter',
            labelname: 'Incident summary'
          }
        }
      },
      {
        componentType: 'PriorityCards',
        criteria: {
          leftOperand: 'MessageStatus',
          condition: 'NOTEQUAL',
          rightOperand: 'incidentRaised'
        },
        props: {
          data: {
            id: 'incidentSummary_card',
            name: 'incidentSummary',
            type: 'card12',
            title: 'Incident summary',
            apiData: '@FormData.raisedByName|generalInfo.raisedBy',
            additional_title: '',
            raisedByName: '',
            classNames: {
              columnType: 'raise-card'
            },
            content: {
              dataFooter: [
                {
                  name: 'Business Service:',
                  description: '',
                  apiData: '@FormData.description|ClientInformation.businessService.value'
                },
                {
                  name: 'Category:',
                  description: '',
                  apiData: '@FormData.description|ClientInformation.category.value'
                },
                {
                  name: 'Sub category:',
                  description: '',
                  apiData: '@FormData.description|ClientInformation.subCategory.value'
                }
              ]
            }
          }
        }
      },
      {
        componentType: 'Accordion',
        criteria: {
          leftOperand: 'MessageStatus',
          condition: 'NOTEQUAL',
          rightOperand: 'incidentRaised'
        },
        pageName: 'RaiseIncident',
        props: {
          data: {
            id: 'incidentSummary_accordion',
            name: 'incidentSummary',
            displayAccordion: true,
            alwaysExpanded: true,
            classNames: {
              columnType: 'raise--summary'
            },
            header: {
              type: 'Simple',
              headerData: {
                title: 'Incident details'
              },
              arrowTooltip: ''
            },
            content: {
              type: 'StaticAccordion',
              groupBy: [
                {
                  labelname: '',
                  listOfFieldIds: [
                    'summary',
                    'descriptionSummary',
                    'impactRangeSlider',
                    'urgencyRangeSlider',
                    'stepsTakenRichtextbox',
                    'commentsRichtextbox'
                  ]
                }
              ]
            }
          }
        },
        groupHeaderStructure: {
          labelData: {
            id: '',
            isRequired: false,
            htmlFor: '',
            type: 'labelDefault',
            labelname: '',
            className: true,
            styling: 'regularFont_18px'
          },
          value: ''
        },
        labelsStructure: {
          labelData: {
            id: '',
            isRequired: false,
            htmlFor: '',
            type: 'labelDefault',
            labelname: '',
            className: true,
            styling: 'regularFont_18px'
          },
          value: ''
        }
      }
    ],
    footerFields: [
      {
        componentType: 'Button',
        criteria: {
          leftOperand: 'MessageStatus',
          condition: 'NOTEQUAL',
          rightOperand: 'incidentRaised'
        },
        props: {
          data: {
            id: 'submitButton',
            name: 'Submit incident',
            type: 'primary',
            buttonType: 'button',
            CreateHandler: 'submitIncident|onClick'
          }
        },
        alignmentClass: 'pull_right'
      },
      {
        componentType: 'Button',
        criteria: {
          leftOperand: 'MessageStatus',
          condition: 'NOTEQUAL',
          rightOperand: 'incidentRaised'
        },
        props: {
          data: {
            id: 'uploadFiles_back',
            name: 'Upload files',
            type: 'secondary',
            location: 'left',
            isIcon: true,
            buttonType: 'button',
            CreateHandler: 'backClickHandler|onClick'
          }
        },
        alignmentClass: 'pull_right'
      },
      {
        componentType: 'Button',
        criteria: {
          leftOperand: 'MessageStatus',
          condition: 'NOTEQUAL',
          rightOperand: 'incidentRaised'
        },
        props: {
          data: {
            id: 'backToTikets',
            name: 'Back to tickets',
            type: 'tertiary',
            buttonType: 'button',
            CreateHandler: 'redirectToTickets|onClick'
          }
        },
        alignmentClass: 'pull_left'
      },
      {
        componentType: 'Button',
        criteria: {
          leftOperand: 'MessageStatus',
          condition: 'EQUAL',
          rightOperand: 'incidentRaised'
        },
        props: {
          data: {
            id: 'viewIncdButton',
            name: 'View incident',
            type: 'tertiary',
            buttonType: 'button',
            CreateHandler: 'redirectToTickets|onClick'
          }
        },
        alignmentClass: 'pull_left'
      },
      {
        componentType: 'Button',
        criteria: {
          leftOperand: 'MessageStatus',
          condition: 'EQUAL',
          rightOperand: 'incidentRaised'
        },
        props: {
          data: {
            id: 'closeOrder',
            name: 'Finished',
            type: 'primary',
            buttonType: 'button',
            CreateHandler: 'redirectToTickets|onClick'
          }
        },
        alignmentClass: 'pull_right'
      }
    ]
  },
  ConfigurationItem: {
    stepSequenceNum: '2',
    currentStepName: 'Configuration item',
    id: 'configurationItem_ID',
    nextStepName: 'IncidentDetails',
    prevStepName: 'YourReference',
    listOfFields: [
      {
        componentType: 'Accordion',
        props: {
          data: {
            displayAccordion: true,
            id: 'incidentDetailsForm',
            name: 'incidentDetailsForm',
            alwaysExpanded: true,
            header: {
              type: 'Title',
              headerData: {
                title: 'Add a full description of the incident'
              }
            },
            content: {
              type: 'FormContent',
              contentData: [
                {
                  componentType: 'Label',
                  props: {
                    data: {
                      id: 'descriptionSummary_label',
                      htmlFor: 'descriptionSummary',
                      type: 'labelDefault',
                      labelname: 'Description',
                      classNames: {
                        columnType: 'summary-txt'
                      }
                    }
                  }
                },
                {
                  componentType: 'TextArea',
                  props: {
                    data: {
                      id: 'descriptionSummary',
                      name: 'descriptionSummary',
                      rows: 5,
                      label: '',
                      maxLength: 4000,
                      title: '',
                      placeholder: '',
                      label_header_left: {
                        labelname: '',
                        type: 'labelDefault',
                        isInline: true,
                        fontSizeType: 'lg'
                      },
                      label_header_right: {
                        labelname: 'characters left',
                        type: 'labelDefault',
                        isInline: true,
                        fontSizeType: 'lg'
                      },
                      classNames: {
                        columnType: 'txt-area des--height pad-top-10'
                      }
                    }
                  }
                }
              ]
            }
          }
        }
      }
    ],
    footerFields: [
      {
        componentType: 'Button',
        props: {
          data: {
            location: 'right',
            isIcon: true,
            id: 'nextButton',
            name: 'Impact',
            type: 'primary',
            buttonType: 'button',
            CreateHandler: 'incidentNextClickHandler|onClick'
          }
        },
        alignmentClass: 'pull_right',
        validateForm: true
      },
      {
        componentType: 'Button',
        props: {
          data: {
            location: 'left',
            isIcon: true,
            id: 'previousButton',
            name: 'Your reference',
            type: 'secondary',
            buttonType: 'button',
            CreateHandler: 'backClickHandler|onClick'
          }
        },
        alignmentClass: 'pull_right',
        validateForm: false
      },
      {
        componentType: 'Button',
        props: {
          data: {
            id: 'previousButton',
            name: 'Back to tickets',
            type: 'tertiary',
            buttonType: 'button',
            CreateHandler: 'redirectToTickets|onClick'
          }
        },
        alignmentClass: 'pull_left',
        validateForm: false
      }
    ],
    validationRules: {
      rules: [
        {
          ruleName: 'REQUIRED',
          applicableFields: [
            'descriptionSummary'
          ],
          message: 'This is mandatory field'
        }
      ],
      messageProps: {
        type: 'warning',
        name: 'warning',
        id: 'validationError',
        lightBackground: true,
        arrowRequired: true,
        messageTitle: 'Sorry, there were @count errors:',
        messageBody: ''
      }
    }
  },
  IncidentDetails: {
    stepSequenceNum: '3',
    currentStepName: 'Incident details',
    id: 'incidentDetails_ID',
    prevStepName: 'ConfigurationItem',
    nextStepName: 'Impact',
    listOfFields: [
      {
        componentType: 'Accordion',
        props: {
          data: {
            displayAccordion: true,
            id: 'incidentDetailsForm',
            name: 'incidentDetailsForm',
            alwaysExpanded: true,
            header: {
              type: 'Title',
              headerData: {
                title: 'Please enter incident details'
              }
            },
            content: {
              type: 'FormContent',
              gridEnable: true,
              contentData: [
                
              ]
            }
          }
        }
      }
    ],
    footerFields: [
      {
        componentType: 'Button',
        props: {
          data: {
            location: 'right',
            isIcon: true,
            id: 'nextButton',
            name: 'Impact',
            type: 'primary',
            buttonType: 'button',
            CreateHandler: 'incidentNextClickHandler|onClick'
          }
        },
        alignmentClass: 'pull_right',
        validateForm: true
      },
      {
        componentType: 'Button',
        props: {
          data: {
            location: 'left',
            isIcon: true,
            id: 'previousButton',
            name: 'Configurations item',
            type: 'secondary',
            buttonType: 'button',
            CreateHandler: 'backClickHandler|onClick'
          }
        },
        alignmentClass: 'pull_right',
        validateForm: false
      },
      {
        componentType: 'Button',
        props: {
          data: {
            id: 'previousButton',
            name: 'Back to tickets',
            type: 'tertiary',
            buttonType: 'button',
            CreateHandler: 'redirectToTickets|onClick'
          }
        },
        alignmentClass: 'pull_left',
        validateForm: false
      }
    ],
    validationRules: {
      rules: [
        {
          ruleName: 'REQUIRED',
          applicableFields: [
            
          ],
          message: 'This is mandatory field'
        }
      ],
      messageProps: {
        type: 'warning',
        name: 'warning',
        id: 'validationError',
        lightBackground: true,
        arrowRequired: true,
        messageTitle: 'Sorry, there were @count errors:',
        messageBody: ''
      }
    },
    initialAPI: [
      {
        queryName: 'BUSINESS_SERVICES',
        responseObjectName: 'businessServices'
      }
    ],
    decorators: [
      
    ]
  },
  Impact: {
    stepSequenceNum: '4',
    currentStepName: 'Impact',
    id: 'impact_ID',
    nextStepName: 'UploadFiles',
    prevStepName: 'IncidentDetails',
    listOfFields: [
      {
        componentType: 'Accordion',
        props: {
          data: {
            displayAccordion: true,
            id: 'incidentDetailsForm',
            name: 'incidentDetailsForm',
            alwaysExpanded: true,
            header: {
              type: 'Title',
              headerData: {
                title: 'Select impact'
              }
            },
            content: {
              type: 'FormContent',
              contentData: [
                {
                  componentType: 'Label',
                  props: {
                    data: {
                      id: 'impactRangeSlider_label',
                      htmlFor: 'impactRangeSlider',
                      type: 'labelDefault',
                      labelname: 'Please select the impact on your business'
                    }
                  }
                },
                {
                  componentType: 'RangeSlider',
                  props: {
                    data: {
                      id: 'impactRangeSlider',
                      name: 'impactRangeSlider',
                      sliderTitle: 'Please select the impact on your business',
                      min: 0,
                      max: 100,
                      step: 25,
                      defaultValue: 0,
                      marks: false,
                      customMarks: {
                        '25': 'Up to 25% of users',
                        '50': '25-75% of users Entire site impacted',
                        '75': '>75% of users Multiple / critical sites impacted'
                      },
                      CreateHandler: 'handleSliderChange|onChange'
                    }
                  }
                }
              ]
            }
          }
        }
      },
      {
        componentType: 'Accordion',
        props: {
          data: {
            displayAccordion: true,
            id: 'incidentDetailsForm',
            name: 'incidentDetailsForm',
            alwaysExpanded: true,
            header: {
              type: 'Title',
              headerData: {
                title: 'Select urgency'
              }
            },
            content: {
              type: 'FormContent',
              contentData: [
                {
                  componentType: 'Label',
                  props: {
                    data: {
                      id: 'urgencyRangeSlider_label',
                      htmlFor: 'urgencyRangeSlider',
                      type: 'labelDefault',
                      labelname: 'Please select the level of urgency'
                    }
                  }
                },
                {
                  componentType: 'RangeSlider',
                  props: {
                    data: {
                      id: 'urgencyRangeSlider',
                      name: 'urgencyRangeSlider',
                      sliderTitle: 'Please select the level of urgency',
                      min: 0,
                      max: 100,
                      step: 25,
                      defaultValue: 0,
                      marks: false,
                      customMarks: {
                        '25': 'Minimal impact (non-time critical) in SLA period',
                        '50': 'Workaround in place Incurring some internal cost sustainable in SLA period',
                        '75': 'Time critical work impacted Loss of revenue situation Safety systems at risk'
                      },
                      classNames: {
                        columnType: 'rc-sliderWrapper'
                      },
                      CreateHandler: 'handleSliderChange|onChange'
                    }
                  }
                }
              ]
            }
          }
        }
      }
    ],
    footerFields: [
      {
        componentType: 'Button',
        props: {
          data: {
            location: 'right',
            isIcon: true,
            id: 'nextButton',
            name: 'Upload files',
            type: 'primary',
            buttonType: 'button',
            CreateHandler: 'incidentNextClickHandler|onClick'
          }
        },
        alignmentClass: 'pull_right',
        validateForm: true
      },
      {
        componentType: 'Button',
        props: {
          data: {
            id: 'saveButton',
            name: 'Incident details',
            location: 'left',
            isIcon: true,
            type: 'secondary',
            buttonType: 'button',
            CreateHandler: 'backClickHandler|onClick'
          }
        },
        alignmentClass: 'pull_right',
        validateForm: false
      },
      {
        componentType: 'Button',
        props: {
          data: {
            id: 'previousButton',
            name: 'Back to tickets',
            type: 'tertiary',
            buttonType: 'button',
            CreateHandler: 'redirectToTickets|onClick',
            labelname: 'Summary'
          }
        },
        alignmentClass: 'pull_left',
        validateForm: false
      }
    ],
    validationRules: {
      rules: [
        {
          ruleName: 'REQUIRED',
          applicableFields: [
            'impactRangeSlider',
            'urgencyRangeSlider'
          ],
          message: 'This is mandatory field'
        }
      ],
      messageProps: {
        type: 'warning',
        name: 'warning',
        id: 'validationError',
        lightBackground: true,
        arrowRequired: true,
        messageTitle: 'Sorry, there were @count errors:',
        messageBody: ''
      }
    }
  }
}

function deleteNonMenu(obj) {
  if (obj.type == "DOC") {
    return true;
  }
  if (obj.nodes) {
    for (var i = 0; i < obj.nodes.length; i++) {
      var res = deleteNonMenu(obj.nodes[i]);
      if (res == true) {
        delete obj.nodes[i];
      }
    }
  }
  return false;
}

for (var i = 0; i < json.length; i++) {
  var result = deleteNonMenu(json[i]);
  if (result == true) {
    delete json[i];
  }
}
console.log(json);
